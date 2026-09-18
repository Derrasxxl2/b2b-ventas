# Metodología de entrega

El diferenciador real. No es que construyamos rápido: es que el cliente **nunca espera a
ciegas** y **nunca recibe una sorpresa**.

Esta metodología se definió y se aplicó en Ullate Roche, y es replicable tal cual.

---

## El ciclo: 7 pasos, 2 puertas

Cada tarea del tablero —cada una de las 83— recorre este ciclo completo. Ciclos
**pequeños**, tarea a tarea. Nada de "gran entrega final".

```
  1. Ideación + criterio de aceptación
         ↓
  ┌──────────────────────────────────┐
  │  ✅ GATE 1 · Aprobación de alcance │  ← el cliente aprueba ANTES de construir
  └──────────────────────────────────┘
         ↓
  3. Ejecución en local (sin tocar producción)
         ↓
  4. Verificación técnica (funciona y no rompe nada)
         ↓
  5. Despliegue a producción (con copia de seguridad y plan de vuelta atrás)
         ↓
  6. Validación en real + prueba de la dueña (UAT con datos reales)
         ↓
  ┌──────────────────────────────────┐
  │  ✅ GATE 2 · Aprobación final     │  ← aceptación → la tarea pasa a Cerrado
  └──────────────────────────────────┘
```

### Los cuatro principios

1. **Dos puertas de aprobación**, antes y después. El cliente firma el alcance antes de
   que gastemos una hora, y firma la aceptación antes de que demos algo por cerrado.
2. **Criterio de "hecho" definido antes de construir.** Si no sabemos cuándo se da por
   bueno, no se empieza.
3. **Todo reversible.** Copia de seguridad y plan de vuelta atrás en cada despliegue.
4. **Tarea a tarea.** El valor llega en días, no en meses.

---

## El tablero

Un tablero (Notion) con una tarjeta por pieza. Cada tarjeta lleva:

| Propiedad | Valores | Para qué sirve |
| --- | --- | --- |
| **Portal** | Público · Alumno · Profesor · Admin · Transversal | A quién afecta |
| **Estado** | Por hacer · En curso · En revisión · Aprobado · Descartado | Dónde está |
| **Etapa** | Los 7 pasos del ciclo | En qué punto exacto del ciclo |
| **Decisión** | Guardar · Por decidir · Descartar | Si entra en el alcance |
| **Aprobación** | Pendiente · Aprobado · Rechazado | Visto bueno de dirección |
| **Prioridad** | Alta · Media · Baja | Orden de ataque |
| **Notas / Acta** | Texto libre | Contexto, decisiones, qué se queda y qué no |

Más tres vistas: **por portal**, **por estado** y **decisiones pendientes**.

### Por qué el tablero es un arma comercial, no solo de gestión

- **El cliente ve su dinero moverse.** Entra al tablero cuando quiere y ve exactamente en
  qué punto está cada cosa. Esto mata el "¿cómo vamos?" semanal.
- **Convierte el feedback en activo.** Cuando el cliente suelta 12 peticiones de golpe,
  no se improvisan: se convierten en 12 tarjetas priorizadas. El cliente siente que le
  escuchamos y nosotros no rompemos lo que funciona.
- **Es el presupuesto de la fase 2.** Todo lo que queda en "Por decidir" es la siguiente
  propuesta comercial, ya escrita y ya validada por el cliente.
- **Es la prueba del trabajo.** Ante una discusión de alcance, el tablero es el acta.

---

## La bitácora

Un log en el propio tablero, lo más reciente arriba, con una entrada por día de trabajo.
Qué se hizo, qué se verificó, qué quedó pendiente y por qué.

Tres usos:

1. **Con el cliente:** transparencia diaria sin reuniones.
2. **Internamente:** cualquiera retoma el proyecto sin preguntar nada.
3. **En ventas:** es de donde sale el caso de éxito. La línea de tiempo del caso Ullate
   Roche está literalmente copiada de aquí. **Si no hay bitácora, no hay caso de éxito.**

---

## Cómo se gestiona el feedback en vivo

Patrón observado en Ullate Roche el día 3, y que es lo que produce el "wow":

1. El cliente suelta una tanda de feedback larga y desordenada.
2. **Se separa en el momento** en dos montones:
   - **Cosmético / superficial** (colores, textos, estados vacíos, orden de pestañas) →
     **se ejecuta ya**, en la misma sesión.
   - **Estructural** (arquitectura, pagos, multi-perfil, integraciones) → **se documenta
     como tarea** con su Gate 1, y se dice en voz alta por qué.
3. Se le devuelve al cliente: *"esto ya está hecho, y estas 12 cosas son cambios en los
   paneles internos; se harán con cuidado para no romper lo que te encanta"*.

Ese último matiz —*"no romper lo que te encanta"*— es lo que convierte una lista de
pendientes en una demostración de criterio profesional.

---

## Reglas de despliegue

- Nunca se despliega sin verificación en local.
- Nunca se despliega sin plan de vuelta atrás.
- El despliegue a producción de una app con datos reales de clientes **requiere OK
  explícito del cliente**. En Ullate Roche el despliegue lo lanzó el propio cliente.
- Tras cada despliegue, **verificación en vivo** documentada en la bitácora.

---

## Lo que esta metodología le quita al cliente

| Miedo del cliente | Cómo lo mata la metodología |
| --- | --- |
| "Me van a cobrar y no me va a gustar" | Gate 1: aprueba el alcance antes de construir |
| "Me van a entregar en 3 meses una cosa que no era" | Ciclos de días, no de meses |
| "Me van a romper lo que funciona" | Todo reversible + verificación antes de desplegar |
| "No me voy a enterar de en qué gastan el tiempo" | Tablero abierto + bitácora diaria |
| "Luego me cobran cada cambio como extra" | Decisión y Aprobación registradas por tarea |

Esto es lo que se cuenta en la llamada de venta. Antes que el stack, antes que las
features. **La metodología es el producto; el software es el entregable.**
