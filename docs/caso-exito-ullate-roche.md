# Caso de éxito · Ullate Roche

> **De 3 personas en administración a 1 —y esa 1 ya no trabaja delante del ordenador.**
> Sistema completo construido, verificado y desplegado en producción en 5 días.

---

## 1. El cliente

**Ullate Roche** — academia de danza, artes escénicas, fitness y deporte.
Centro comercial, zona norte de Madrid (Alcobendas / La Moraleja).

- **29 actividades** en catálogo (ballet, rítmica, flamenco, funky, cheerleading, boxeo,
  fitness de mañanas…).
- Alumnado de **3 a 80+ años**: peques, infantil, juvenil, adultos.
- Mayoría de mujeres salvo en boxeo. Padres que traen a los niños buscando resultados
  reales, no una extraescolar de guardería.
- Precio por actividad según días/semana, con bonos; ilimitado con cuota fija en boxeo y
  en el bono de mañanas.
- Matrícula de 50 €, que en baile se renueva cada año y en deporte se paga una sola vez.

Contacto principal: **Miriam** (dirección). Segunda: **Patri**.
Origen del lead: **referral** — amigos de Pablo (Sotomora), cliente previo.

### Cómo llegamos

Entramos por la puerta de **estrategia de redes sociales**, no por software.
En el onboarding (17/02) salió la verdad: no tenían reserva online, la captación era
boca a boca, la clase de prueba gratis convertía al **95 %** y **nadie la podía reservar
sin llamar por teléfono**. Miriam dijo textualmente que estaba **desbordada**.

> **Lección comercial:** el CRM no se vendió como CRM. Se vendió porque en una conversación
> de marketing apareció un cuello de botella operativo que costaba tres sueldos.

---

## 2. El dolor, en concreto

Antes del sistema, esto lo hacían personas a mano:

| Tarea | Cómo se hacía antes |
| --- | --- |
| Reservar una clase de prueba | Llamada de teléfono → apuntar en papel/Excel |
| Saber quién viene hoy a clase | Listado impreso, profesor dictando a recepción |
| Pasar lista | Papel → transcripción manual |
| Control de cuotas y cobros | Excels cruzados (ACTIVOS + cobrados) |
| Altas, bajas y pausas | Presencial en recepción, obligatoriamente |
| Recuperar una clase perdida | Negociación caso a caso en mostrador |
| Horas trabajadas de cada profesor | Cálculo manual para nómina/factura |
| Ocupación real de cada clase | No existía |
| Avisar a un grupo | Llamadas / WhatsApp individuales |

Tres personas en administración sosteniendo eso. Y todavía se perdían leads: **un
formulario de contacto no existía**, la web no vendía, y la clase de prueba —su mejor
arma, con 95 % de conversión— dependía de que alguien cogiera el teléfono.

---

## 3. Qué construimos

Un sistema de **cuatro portales sobre una sola base de datos**. No cuatro herramientas:
una sola, con cuatro caras según quién entra.

```
                    ┌───────────────────────────────┐
                    │   Base de datos única (Turso)  │
                    │  alumnos · clases · pagos ·    │
                    │  asistencia · familias · horas │
                    └───────────────┬───────────────┘
                                    │
        ┌───────────────┬───────────┼───────────┬───────────────┐
        │               │           │           │               │
   ┌────▼────┐    ┌─────▼────┐ ┌────▼────┐ ┌────▼─────┐         │
   │ PÚBLICO │    │  ALUMNO  │ │ PROFESOR│ │  ADMIN   │         │
   │  (web)  │    │  (app)   │ │  (app)  │ │(dirección)│        │
   └─────────┘    └──────────┘ └─────────┘ └──────────┘         │
    capta          se gestiona   pasa lista   ve y decide       │
    y reserva      solo          y ficha                        │
                                                                 │
                            ┌────────────────────────────────────┘
                            │  Integraciones
                            │  Stripe · SEPA · Holded · WhatsApp (Meta)
                            └────────────────────────────────────
```

**El principio de diseño que lo cambia todo:** cada tarea administrativa se empuja hacia
la persona que tiene el interés en hacerla. El alumno se apunta solo porque quiere la
plaza. El profesor pasa lista porque está en la sala. Dirección solo mira lo que ya está
calculado. Administración deja de ser el intermediario de todo.

El inventario completo —**83 piezas** con su estado real— está en
[`catalogo-crm.md`](catalogo-crm.md).

---

## 4. La línea de tiempo real

Sacada del log de entrega del proyecto. Esto es lo que se puede defender con documentos.

### Día 1 — 14/09/2026
- Cruce de los Excels del cliente (ACTIVOS + cobrados): **emails de 21 alumnos pagadores**
  cargados. Se documentan los 7 que no se pudieron (3 sin ficha, 2 hermanos con email
  compartido, 2 sin email en origen).
- **Rol Profesor completo**: web propia con Hoy/Semana y **pasar lista (Vino/Faltó)**.
- En admin, **suma de listas por clase** (vinieron / faltaron / sin marcar).
- Se levanta el sitio en producción con **29 alumnos de boxeo importados**.
- Base de datos y proyecto **independientes** del sistema completo del centro.

### Día 2 — 15/09/2026
- Alta de la profesora **María**, verificada en producción.
- **75 alumnos** apuntados en las clases de la semana (datos de prueba para estresar el
  sistema con volumen real).
- Se documenta el bloqueo de SMTP: sin correo configurado no salen accesos ni avisos.

### Día 3 — 16/09/2026 (el día grande)
- Se crea el **tablero de gestión en Notion**: 62 tareas por portal + vistas por portal,
  por estado y por decisiones pendientes. Y se define la **metodología de 7 pasos con 2
  puertas de aprobación**.
- **Gate 1 aprobado** del scope de la web pública premium de toda la academia.
- **Web pública** rehecha (Next.js + React + Tailwind) tras el feedback del cliente
  —*"parecía IA, todo cuadrado"*—, con fotos reales, filtro por edad y catálogo en vivo
  contra el backend.
- **Flujo completo de clase de prueba CON login**: registro autoservicio (nombre,
  apellidos, DNI, teléfono, fecha de nacimiento → categoría por edad), solo aparecen
  actividades **aptas por edad** y **con plaza**, reglas de una prueba por actividad y una
  por día. Probado de punta a punta.
- Política de privacidad + consentimiento obligatorio en el alta (RGPD).
- **Tanda grande de feedback en vivo**: el cliente se va a comer, vuelve y está ejecutado.
  Rojo → granate en los tres paneles, actividades ya probadas apagadas, y **12 peticiones
  más documentadas como tareas** en vez de improvisadas.
- **Multi-perfil familiar, fase 1**: una madre, un email, varios hijos, cambio de perfil.
  Probado de punta a punta: madre crea cuenta para su hija de 11 → le salen las clases
  infantiles → añade una segunda hija → cambia entre perfiles.
- **Desplegado a producción** y verificado en vivo.

### Día 4 — 17/09/2026
- **Portal de profesor cerrado y aprobado por el cliente**: "Mis horas" (horas trabajadas
  del mes, fijas + cubiertas, con histórico de 6 meses), perfil con foto, vacaciones y
  ausencias **con reasignación automática**, QR con copiar enlace, eliminar profesor
  desde admin.
- Reorganización del portal de alumno: bonos integrados en Pagos, textos de forma de pago
  unificados, estado vacío del inicio con acciones directas en vez de *"pásate por
  recepción"*.
- Repaso completo del portal de alumno y **nuevas peticiones del cliente documentadas**.

### Día 5 y siguientes — integraciones
- **Stripe + SEPA + cobro en metálico**: cuotas, recibos PDF, bonos, webhook.
- **Holded**: al marcarse un pago como pagado (online o en caja) se emite la factura
  automáticamente, con job de reintento.
- **WhatsApp contra la Graph API de Meta**: webhook de entrada, envío, histórico de
  conversaciones e identificación del teléfono con la ficha del alumno.

---

## 5. Resultados

### Verificado (documentado en el log de entrega)

| | |
| --- | --- |
| **5 días** | De cero a sistema en producción usado por alumnos, profesores y dirección |
| **4 portales** | Público, alumno, profesor y dirección sobre una única base de datos |
| **83 piezas** | Funcionalidades identificadas, priorizadas y trazadas una a una |
| **29 actividades** | Todo el catálogo de la academia, no un piloto |
| **2 puertas de aprobación** | Por tarea. Cero sorpresas en la entrega final |
| **0 vuelta atrás** | Ningún despliegue revertido |

### Testimonio del cliente — ⚠️ pendiente de recoger por escrito

> *"De 3 secretarias a 1. Y esa 1 ya no trabaja delante del ordenador."*

**Acción pendiente antes de usar esto en material público:** pedir a Miriam el testimonio
por escrito (o en vídeo, mejor) con esa frase y permiso de uso. Sin eso, en frío se usa
la versión verificable: *"pasaron de tres personas en administración a una"*, atribuida
al cliente, no afirmada por nosotros.

### Qué desapareció exactamente

Lo que antes consumía tres sueldos y ahora no existe como tarea:

- Coger el teléfono para reservar una clase de prueba → **el alumno la reserva solo**, y
  el sistema ya filtra por edad y por plaza libre.
- Transcribir listas de asistencia → **el profesor las marca en la sala**.
- Calcular horas de cada profesor para la nómina → **se calculan solas**, con histórico.
- Cuadrar quién ha pagado → **Stripe/SEPA + Holded emiten la factura solas**.
- Gestionar altas, bajas, pausas y cambios en mostrador → **autoservicio en la app**.
- Perseguir a la familia con tres hijos y un solo email → **multi-perfil familiar**.

---

## 6. Por qué se pudo hacer en 5 días

Tres razones, y ninguna es "trabajamos mucho":

1. **Metodología de ciclos cortos con doble aprobación.** Nada de gran entrega final.
   Tarea a tarea, con criterio de "hecho" definido *antes* de construir. El cliente no
   espera tres meses para descubrir que no era eso. Ver [`metodologia.md`](metodologia.md).

2. **Stack que despliega en minutos.** Ver [`stack.md`](stack.md).

3. **Feedback en vivo, ejecutado en vivo.** El día 16 el cliente dio una tanda de
   feedback, se fue a comer y volvió con parte ejecutada y el resto documentado como
   tareas priorizadas. Eso es lo que genera la frase *"no me lo puedo creer"*.

---

## 7. Qué se vende con este caso

Los cinco momentos que mueven una venta, ordenados por potencia:

1. **"Se fue a comer y cuando volvió estaba hecho."** Velocidad tangible.
2. **"La clase de prueba convertía al 95 % y solo se podía reservar por teléfono."**
   El dolor que el prospecto reconoce en su propio negocio.
3. **"El profesor ve solo lo suyo, el alumno solo lo suyo, dirección lo ve todo."**
   Hiperpersonalización explicada en una frase.
4. **"Las horas para la nómina se calculan solas."** El ahorro que un dueño entiende sin
   traducción.
5. **"Parecía IA, todo cuadrado" → lo rehicimos.** Que aceptamos el juicio estético del
   cliente y rehacemos. Mata la objeción de "esto lo hace cualquiera con IA".

---

## 8. Material pendiente de producir

- [ ] Testimonio escrito o en vídeo de Miriam, con permiso de uso.
- [ ] Capturas de los 4 portales (anonimizadas: sin nombres ni DNIs reales).
- [ ] Vídeo de 60-90 s: recorrido público → alumno → profesor → dirección.
- [ ] Cifra de ahorro en euros/año, calculada con el cliente (3 sueldos de administración
      a jornada parcial en Madrid ≈ punto de partida para la conversación).
- [ ] Dato de conversión de la web nueva a clase de prueba, a 30 y 90 días.
