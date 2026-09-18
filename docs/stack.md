# Stack y arquitectura

Por qué podemos entregar en días lo que una consultora entrega en meses, y por qué el
coste de mantenimiento para el cliente es bajo.

Este es el stack real del sistema de Ullate Roche.

---

## Arquitectura

```
┌─────────────────────────┐        ┌──────────────────────────┐
│  Web pública (Next.js)   │──BFF──▶│   Backend (Express)      │
│  React + Tailwind        │        │   Auth · roles · lógica  │
│  Vercel                  │        │   Vercel                 │
└─────────────────────────┘        └───────────┬──────────────┘
                                                │
   ┌──────────────┬──────────────┬──────────────┼──────────────┐
   │              │              │              │              │
┌──▼───┐   ┌──────▼─────┐  ┌─────▼────┐  ┌──────▼────┐  ┌──────▼──────┐
│Turso │   │   Stripe    │  │  Holded  │  │ WhatsApp  │  │  Supabase   │
│ (BD) │   │ Tarjeta+SEPA│  │ Facturas │  │ Graph API │  │ Histórico   │
└──────┘   └────────────┘  └──────────┘  └───────────┘  │ conversac.  │
                                                          └─────────────┘
```

Los tres paneles internos (alumno, profesor, admin) viven servidos por el backend.
La web pública es una app Next independiente que consume el backend vía endpoints
públicos (`/api/public/catalog`) y proxies BFF que gestionan las cookies de sesión.

---

## Componentes y por qué cada uno

| Capa | Tecnología | Por qué |
| --- | --- | --- |
| **Base de datos** | Turso (SQLite distribuido) | Una base por cliente, aislada. Se crea en segundos. Coste cercano a cero en el volumen de una pyme |
| **Backend** | Node + Express | Sin framework pesado. Legible, modificable en caliente, sin ceremonia |
| **Web pública** | Next.js 16 + React + Tailwind | Rendimiento y SEO de serie; permite diseño premium real |
| **Animación** | Framer Motion | Microinteracciones que separan "premium" de "plantilla" |
| **Hosting** | Vercel | `deploy --prod` en minutos, previews por rama, vuelta atrás inmediata |
| **Pagos** | Stripe (tarjeta + SEPA) | Domiciliación real en España, webhooks, recibos |
| **Facturación** | Holded | Lo que ya usa la gestoría española media |
| **Mensajería** | WhatsApp Graph API (Meta) | El canal donde de verdad están los clientes de una pyme |
| **Conversaciones** | Supabase | Histórico de mensajes ligado a la ficha del alumno |
| **Tipografía** | Fraunces + Instrument Sans | **Nunca Inter ni Roboto**: son la firma visual de "esto lo ha hecho una IA" |

---

## Las cuatro decisiones que hacen posible los 5 días

### 1. Una base de datos y un proyecto por cliente

Nada de multi-tenant compartido. Cada cliente tiene su base y su despliegue.

- Sin migraciones que afecten a otros clientes.
- Se puede hiperpersonalizar el modelo de datos sin romper nada.
- Si un cliente se va, se le entrega su base y se acabó.
- Y permite algo que hicimos en Ullate: **levantar una versión reducida** (solo boxeo)
  como proyecto y base independientes, para probar en real sin tocar el sistema grande.

### 2. Integraciones "apagadas por defecto"

Stripe, Holded y WhatsApp están **construidos y en el código, sin claves**. No hacen nada
hasta que se pegan las credenciales del cliente.

Esto cambia la conversación comercial: la integración **no es un proyecto futuro**, es un
interruptor. *"Ya está hecho; en cuanto me des tu clave de Holded, tus facturas salen
solas."*

### 3. Portales sobre una sola base, no cuatro herramientas

Cada rol ve una cara distinta de los mismos datos. Un alumno que pasa lista no existe; un
profesor que ve los DNIs no existe. El permiso está en la arquitectura, no en una
configuración que alguien puede tocar.

### 4. Vuelta atrás siempre disponible

Previews por rama, despliegue a producción explícito y copia de seguridad antes de cada
uno. Es lo que permite mover rápido sin miedo: **la velocidad viene de poder deshacer**.

---

## Diseño: la parte que casi se pierde

Feedback literal del cliente sobre la primera web: **"parecía IA, todo cuadrado"**.

Se rehízo entera. Lecciones convertidas en checklist obligatorio:

- **Identidad propia.** Ni plantilla, ni clichés del sector.
- **Tipografía con intención.** Display + sans. Nunca las fuentes por defecto.
- **Paleta contenida** y coherente con la marca (en Ullate: carbón, crema, granate, nude,
  dorado puntual — y el granate se llevó también a los tres paneles internos).
- **Fotografía real del cliente**, no stock.
- **Formas con carácter** (en Ullate: el arco teatral) en vez de rectángulos apilados.
- **Microinteracciones** que acompañen, no que decoren.
- **La acción principal siempre a mano** (reservar prueba, WhatsApp).

> Esto no es estética: es lo que impide que el cliente piense *"esto me lo hago yo con una
> IA en una tarde"*. **El diseño es la defensa del precio.**

---

## Coste de operación para el cliente

Órdenes de magnitud al volumen de una pyme de servicios (decenas a pocos cientos de
usuarios activos):

| Partida | Coste |
| --- | --- |
| Base de datos (Turso) | Céntimos a pocos euros / mes |
| Hosting (Vercel) | Plan de entrada |
| Pagos (Stripe) | Comisión por transacción, sin cuota fija |
| Facturación (Holded) | Lo que el cliente **ya paga** |
| WhatsApp (Meta) | Por conversación |
| Correo (SMTP) | Gratis o casi |

Argumento de venta directo: **la infraestructura cuesta menos que una comida al mes**.
Lo que se paga es el sistema y quien lo mantiene, no la licencia por usuario que cobra un
SaaS —y que sube cada vez que el negocio crece.

---

## Qué NO hacemos (y se dice en la venta)

- **No somos software contable.** Generamos los datos; la parte legal la lleva la gestoría
  del cliente. Conserva a su gestor.
- **No hacemos multi-tenant genérico.** Si lo que quiere es un SaaS estándar y barato, no
  somos nosotros.
- **No migramos dominios ni correo corporativo** salvo que se contrate aparte.
- **No entregamos sin datos reales cargados.** Un sistema vacío no se adopta: en Ullate se
  importaron los alumnos, se cruzaron los Excels de pagos y se sembró con volumen real
  antes de enseñarlo.
