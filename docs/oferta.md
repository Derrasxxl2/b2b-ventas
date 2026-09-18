# La oferta: cómo se empaqueta y se pone precio

> ⚠️ **Las cifras de este documento son una propuesta de estructura, no precios
> decididos.** Faltan dos datos que solo tenéis vosotros: qué se cobró en Ullate Roche y
> cuál es vuestro coste real por proyecto. Ajustad los números; la estructura sí es
> defendible tal cual.

---

## El principio: no se vende software, se vende un puesto de trabajo

El error de partida sería cotizar por horas o por funcionalidades. La conversación
correcta es esta:

> *"¿Cuánto te cuesta al año la persona que hace esas tareas a mano?"*

Un puesto de administración a jornada completa en España le cuesta a la empresa, con
seguridad social, del orden de **25.000-35.000 € al año**. Si el sistema elimina uno —o
dos, como en Ullate Roche—, cualquier precio de cinco cifras **se amortiza en meses**.

Ese es el marco. Todo lo demás es aritmética.

---

## Estructura recomendada: tres piezas

### 1 · Implantación (pago único)

El sistema construido, cargado con sus datos reales y en producción.

**Rango orientativo: 6.000 - 15.000 €** según número de portales, integraciones y
complejidad del modelo de datos.

Incluye siempre:
- Reunión de alcance y checklist de funcionalidades cerrada.
- Tablero de entrega abierto al cliente, con las dos puertas de aprobación.
- Los portales acordados, sobre una base de datos propia y aislada.
- **Migración de sus datos reales** (Excels, listados, lo que tengan).
- Despliegue a producción y verificación en vivo.
- Formación al equipo del cliente.

### 2 · Mantenimiento y evolución (cuota mensual)

Aquí está el negocio recurrente, y es donde el tablero hace su trabajo: todo lo que quedó
en "Por decidir" es el roadmap ya validado por el cliente.

**Rango orientativo: 300 - 900 €/mes** según nivel.

| Nivel | Qué incluye |
| --- | --- |
| **Base** | Alojamiento, copias de seguridad, correcciones, soporte por email |
| **Evolución** | Lo anterior + una bolsa mensual de horas de nuevas funcionalidades |
| **Socio** | Lo anterior + revisión trimestral del negocio con datos del sistema |

> Sin cuota mensual, un proyecto así muere. Y sin ella, el cliente se queda con una foto
> fija de su negocio en el momento en que se la entregamos.

### 3 · Fase 2 (proyectos cerrados)

Las piezas grandes del catálogo que no entraron en la fase 1 se cotizan como proyectos
independientes: pasarela de pago completa, WhatsApp, app instalable, asistente de IA,
módulo de eventos y entradas…

**Ventaja estructural:** ya están especificadas en el tablero y ya las ha visto el
cliente. La venta de la fase 2 no requiere descubrimiento: requiere un email.

---

## Anclaje: por qué no somos caros

| Alternativa del cliente | Coste real |
| --- | --- |
| Mantener a la persona que lo hace a mano | 25.000-35.000 €/año, **para siempre** |
| CRM SaaS de sector | 50-150 €/usuario/mes + implantación + **no hace lo suyo** |
| Desarrollo a medida con una consultora | 40.000-100.000 € y 6-12 meses |
| Nosotros | Implantación de 5 cifras bajas + cuota + **vivo en días** |

Tres frases para la llamada:

- *"La infraestructura le cuesta menos que una comida al mes. Lo que paga es el sistema,
  no una licencia por empleado que le sube cada vez que crece."*
- *"Un SaaS le hace adaptar su negocio al software. Nosotros hacemos lo contrario."*
- *"Si en seis meses no le ha ahorrado lo que cuesta, es que no hemos entendido su
  negocio."*

---

## Condiciones que protegen la entrega

- **50 % al inicio, 50 % en el Gate 2 de la última tarea de la fase 1.** El cliente paga
  el resto cuando lo ha visto funcionando con sus datos.
- **El alcance se cierra por escrito** en el tablero antes de empezar. Lo que llega
  después entra como tarea y se prioriza; no se regala ni se discute.
- **Los datos son del cliente.** Su base es suya y se la llevamos si se va. Se dice en la
  primera reunión: mata la objeción del secuestro y no cuesta nada.
- **Las credenciales las pone el cliente** (Stripe, Holded, WhatsApp, SMTP). Se avisa al
  principio porque es la causa número uno de bloqueo: en Ullate Roche, el SMTP sin
  configurar dejó en pausa el envío de accesos y los recordatorios de clase.

---

## El gancho de entrada: la auditoría de operativa

Para prospectos que no están listos para firmar cinco cifras.

**Una sesión de 90 minutos**, de pago (400-900 €), con un entregable:

1. Mapa de todo lo que su equipo hace a mano hoy.
2. Cuantificación en horas/semana y en euros/año.
3. Propuesta de qué desaparece, en qué orden y con qué impacto.
4. El tablero del proyecto, ya montado, con su alcance.

**El importe se descuenta íntegro de la implantación si contrata.**

Tres razones para hacerlo así:
- Filtra a quien no tiene presupuesto sin gastar tu tiempo gratis.
- Convierte el descubrimiento en un entregable que el cliente ya valora.
- El que paga 600 € por una auditoría está mucho más cerca de firmar que el que pide
  "una propuesta sin compromiso".

---

## Decisiones pendientes

- [ ] ¿Qué se facturó realmente en Ullate Roche? Es el ancla de todo lo demás.
- [ ] ¿Coste real por proyecto? Sin esto no hay margen calculable.
- [ ] ¿Cerramos por vertical (academias) o vamos horizontal? Ver [`icp.md`](icp.md).
- [ ] ¿La auditoría de entrada entra en el proceso estándar o solo para dudosos?
