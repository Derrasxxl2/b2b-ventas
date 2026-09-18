# Catálogo · Qué incluye un CRM hiperpersonalizado

Inventario real del sistema de Ullate Roche: **83 piezas**, trazadas una a una en el
tablero de entrega. Este documento sirve para dos cosas:

1. **Vender.** Enseñar al prospecto la profundidad real de lo que entregamos.
2. **Cotizar.** Usarlo como checklist en la reunión de alcance: se marca lo que entra en
   la primera entrega y lo que va a segunda fase.

## Leyenda de estado

| | |
| --- | --- |
| ✅ | **En producción.** Vivo, usado a diario, verificado |
| 🔨 | **Construido**, verificado en local, pendiente de desplegar |
| 📋 | **En catálogo.** Identificado y especificado; se cotiza aparte |
| 🔒 | **Bloqueado** por una decisión o una credencial del cliente |

---

## A · Portal público (la web que capta)

La cara comercial. Su único trabajo es convertir a un desconocido en una reserva.

| # | Pieza | Estado |
| --- | --- | --- |
| 1 | Web pública informativa: actividades, horarios, precios | 🔨 |
| 3 | **Reserva de clase de prueba con login**, coordinada con plaza libre y edad | 🔨 |
| 64 | Actividades ya probadas se muestran apagadas, con enlace a contratar | 🔨 |
| 2 | Inscripción pública online con firma | 📋 |
| 8 | Formulario de contacto / captación de leads | 📋 |
| 66 | Ficha por actividad + popup "i" con resumen corto al reservar | 📋 |
| 4 | Compra de bonos y clases sueltas online | 📋 |
| 5 | Bonos regalo con código canjeable | 📋 |
| 6 | Venta de entradas a eventos y festivales | 📋 |
| 7 | App instalable (PWA) + avisos push | 📋 |
| 80 | Pedir plaza en clase llena (over-aforo) con aprobación del entrenador | 📋 |

**Detalle del flujo de prueba** (la pieza que más vende):

1. El visitante navega el catálogo y filtra por **persona/edad** (peque 3-5 · infantil
   6-12 · juvenil 13-17 · adulto 18+), quitable con "Ver todas".
2. Pulsa "Reservar prueba" → crea cuenta al momento (nombre, apellidos, DNI, email,
   teléfono, fecha de nacimiento) o entra.
3. Ve **solo sesiones con plaza libre de actividades aptas para su edad**.
4. Reserva. Reglas automáticas: **una prueba por actividad** y **una por día**.
5. El profesor ve el nombre. Dirección ve DNI, email y teléfono.
6. Menores: la cuenta la lleva el adulto responsable, con los datos del alumno.

---

## B · Portal del alumno (la app que le quita trabajo a recepción)

Cada cosa que el alumno hace aquí es una cosa que administración deja de hacer.

| # | Pieza | Estado |
| --- | --- | --- |
| 9 | Login, recuperar y cambiar contraseña | ✅ |
| 10 | Reservar y cancelar clases, respetando días y cupo | ✅ |
| 11 | **Días fijos**: fijar su horario semanal ("Mis fijas") | ✅ |
| 19 | Perfil y datos personales | ✅ |
| 74 | Editar perfil: nombre, email, forma de pago | 🔨 |
| 65 | Su clase de prueba en el inicio, con **reprogramar y cancelar** | 🔨 |
| 69 | Baja con **fecha "a partir de" y motivo obligatorios** | 🔨 |
| 73 | Forma de pago "pago físico en recepción" | 🔨 |
| 71 | **Multi-perfil familiar**: varios hijos, un email, cambio de perfil | 🔨 |
| 68 | Pausar clases en autoservicio + **parar el cobro** si dura +1 mes | 📋 |
| 72 | Contratar una actividad extra desde su panel | 📋 |
| 62 | Contratar clases completas (matrícula + pago) desde la app | 📋 |
| 12 | Ver y pagar cuotas con descuentos (Stripe) | 📋 |
| 15 | Comprar bonos y clases sueltas | 📋 |
| 70 | Bonos con precio ajustado por actividad | 📋 |
| 17 | Recibos en PDF descargables | 📋 |
| 14 | Recordatorio de clase con botón "No puedo ir" | 🔒 SMTP |
| 13 | Lista de espera: "avísame si se libera" | 📋 |
| 16 | Solicitudes: pausa, cambio de grupo, baja | 📋 |
| 18 | Avisos push al móvil | 📋 |
| 79 | Centro de avisos con histórico y marcar como leído | 📋 |
| 78 | Coherencia de recuperaciones en los tres sitios donde aparecen | 📋 |
| 81 | Filtro por edad al contratar + **override de admin** por alumno | 📋 |

**Multi-perfil familiar**, en detalle —resuelve un caso que rompe casi todos los CRMs
genéricos: una madre con tres hijos y un solo email. Cuenta titular con check "la cuenta
es para mi hijo/a", pago por familia, cuotas de familia, alta de perfiles en autoservicio
y cambio de perfil desde el menú del avatar.

---

## C · Portal del profesor

| # | Pieza | Estado |
| --- | --- | --- |
| 20 | Login de profesor | ✅ |
| 22 | Ver sus clases: vista **Hoy** y vista **Semana** | ✅ |
| 21 | **Pasar lista** (Vino / Faltó) desde la sala | ✅ |
| 24 | Asignación de clases por profesor (varios profesores) | ✅ |
| 25 | Pedir baja de una clase + sustituciones | ✅ |
| 26 | Avisos al profesor: sustitución, lista pendiente | ✅ |
| — | **"Mis horas"**: horas del mes (fijas + cubiertas) + histórico de 6 meses | ✅ |
| — | Perfil de profesor con foto | ✅ |
| — | **Vacaciones y ausencias con reasignación automática** | ✅ |
| — | QR de clase con "copiar enlace" | ✅ |
| — | Eliminar profesor desde admin | ✅ |
| 27 | Informe de horas por profesor y mes (base de nómina/factura) | 📋 |

> "Mis horas" cuenta **solo las clases ya dadas**: no proyecta futuro, los meses sin datos
> salen a cero. Se especificó así a propósito, porque un profesor que ve horas proyectadas
> reclama por horas que no ha trabajado.

---

## D · Portal de dirección (admin)

Donde se ve el negocio sin pedirle nada a nadie.

| # | Pieza | Estado |
| --- | --- | --- |
| 29 | **Panel Hoy** con estadísticas | ✅ |
| 30 | Semana y ocupación | ✅ |
| 31 | Asistencia: suma de listas (vinieron / faltaron / sin marcar) | ✅ |
| 33 | Alumnos y matrículas: alta y edición | ✅ |
| 36 | Horarios: crear y editar clases y cupos | ✅ |
| 38 | Registro de clases de prueba | ✅ |
| 49 | Contraseñas visibles para dirección | ✅ |
| 34 | Completar emails de alumnos | 🔨 |
| 75 | **Holded**: factura automática al marcarse un pago como pagado | 🔨 |
| 35 | Enviar accesos a los alumnos por email | 🔒 SMTP |
| 46 | **Informes**: ingresos, ocupación, LTV, horas, bajas | 📋 |
| 39 | Pagos: generar cuotas con descuentos | 📋 |
| 40 | Cobro automático: domiciliaciones y reintentos | 📋 |
| 41 | Pedir un cobro puntual (festival, material) | 📋 |
| 47 | Ajustes de matrícula y descuentos | 📋 |
| 37 | Festivos: días sin clase | 📋 |
| 42 | Comunicados: email a grupos | 📋 |
| 43 | Solicitudes: pausa, cambio, baja | 📋 |
| 44 | Inscripciones: revisar altas públicas | 📋 |
| 45 | Eventos y festivales | 📋 |
| 82 | Emitir **factura completa** además del recibo (NIF, IVA, serie propia) | 📋 |
| 48 | **Asistente de IA** dentro del panel | 📋 |

---

## E · Transversal: cobros, contabilidad, comunicación, seguridad

Lo que no se ve pero es lo que hace que el sistema sustituya a personas.

### Cobros y contabilidad

| # | Pieza | Estado |
| --- | --- | --- |
| 77 | **Cobros Stripe + SEPA + metálico**: cuotas, recibos PDF, bonos, webhook | 🔨 🔒 claves |
| 75 | **Holded**: emisión automática de factura, con job de reintento | 🔨 🔒 clave |
| 55 | Export mensual de ingresos en CSV (para gestoría) | 📋 |
| 56 | Export de horas por profesor (para nóminas) | 📋 |
| 59 | Configurar Stripe | 🔒 cliente |

> **Postura sobre contabilidad:** el sistema **genera los datos** (ingresos, horas,
> facturas). La parte legal la lleva la gestoría o el software fiscal. No nos metemos a
> ser un software contable, y eso es un argumento de venta, no una limitación: el cliente
> conserva a su gestor y nosotros le damos datos limpios.

### Comunicación

| # | Pieza | Estado |
| --- | --- | --- |
| 76 | **WhatsApp** vía Graph API de Meta: webhook de entrada, envío, histórico de conversaciones en Supabase, enlace del teléfono con la ficha del alumno, panel en admin | 🔨 🔒 claves |
| 50 | Envío de correo (SMTP) | 🔒 cliente |
| 67 | Foto de perfil personalizable en los tres paneles | 📋 |

### Seguridad, datos y operación

| # | Pieza | Estado |
| --- | --- | --- |
| — | Política de privacidad + **consentimiento obligatorio** en el alta | ✅ |
| 58 | RGPD / protección de datos personales | 📋 |
| 51 | Cambiar contraseñas por defecto | 📋 |
| 57 | Copias de seguridad de la base de datos | 📋 |
| 52 | Importar alumnos pagados sin ficha | 📋 |
| 53 | Resolver hermanos que comparten correo | 📋 |
| 54 | Conseguir los emails de alumnos que faltan | 📋 |
| 60 | Decidir nombre y dominio definitivo | 📋 |
| 61 | Decidir aforos definitivos de las clases | 📋 |
| 63 | Identidad de color en los tres paneles | 🔨 |

---

## Cómo usar esto en una reunión de alcance

1. **No enseñar la tabla entera de entrada.** Abruma y desplaza la conversación a features.
2. Preguntar primero **qué hacen a mano hoy** (ver [`../ventas/discovery.md`](../ventas/discovery.md)).
3. Cada respuesta se marca aquí. Lo marcado se convierte en el alcance de la fase 1.
4. Lo no marcado **se enseña al final**, como catálogo: *"y esto es lo que se puede añadir
   después, sin rehacer nada"*. Eso es lo que abre la segunda venta.

**Regla de oro:** la fase 1 se cierra con lo mínimo que elimina un puesto de trabajo de
administración. Todo lo demás es fase 2. Un sistema vivo en 5 días vende la fase 2 sola;
un sistema perfecto en 3 meses no llega a entregarse.
