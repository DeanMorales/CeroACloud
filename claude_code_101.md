# Guía Completa de Claude Code

## ¿Qué separa a Claude Code de Claude?

Si has usado Claude.ai antes, quizás te preguntes qué hace diferente a Claude Code. A diferencia de Claude.ai, Claude Code tiene acceso directo a tus archivos, tu terminal y toda tu base de código. En lugar de copiar y pegar código de un lado a otro, entra y hace el trabajo él mismo.

**El diferenciador clave es que Claude Code funciona como un Agente de IA.**

---

## ¿Qué es un Agente?

Un Agente de IA es software que puede interactuar con su entorno y realizar acciones para completar un objetivo definido. En su esencia, esto funciona al tener un modelo de lenguaje grande operando en un bucle en tiempo real.

Los Agentes de IA pueden tener acceso a:

- Herramientas
- Servicios externos
- Otros Agentes de IA

> Todo esto para ayudar a alcanzar sus objetivos.

---

## ¿Qué puede hacer realmente Claude Code?

Esto es lo que eso significa en la práctica:

| Capacidad | Descripción |
|-----------|-------------|
| **Leer tu base de código** | Explicar una función o rastrear un error en todo tu código |
| **Editar archivos** | Refactorizar funciones y actualizar cada archivo que la referencia |
| **Ejecutar comandos** | Correr scripts de compilación, pruebas, instalar paquetes |
| **Buscar en la web** | Obtener documentación o referencias de API actualizadas |

---

## Usar Claude Code de manera efectiva

Para usar Claude Code de manera efectiva, ten en cuenta estos tres conceptos:

### 1. La ventana de contexto

Piensa en esto como la **memoria de trabajo** de Claude. Puede contener mucho, pero no todo a la vez.

> Aquí es donde entra el aspecto "agéntico": Claude encuentra formas estratégicas de localizar respuestas dentro de tu base de código sin cargar todo en el contexto.

### 2. Pide permiso

Por defecto, Claude Code te preguntará antes de ejecutar comandos o hacer cambios. Siempre tienes el control, ya sea que prefieras un enfoque más práctico o más autónomo.

### 3. Puede cometer errores

Como cualquier herramienta, Claude Code no es perfecto. Podría malinterpretar tu intención, introducir un error o sobrediseñar una solución. Mantenerte involucrado te ayuda a detectar estos problemas a tiempo.

---

> **Resumen:** Claude Code es una herramienta de codificación agéntica. Lee tu base de código, edita tus archivos, ejecuta comandos y se conecta a herramientas externas para ayudarte a entregar más rápido. Puedes usarlo hoy en tu terminal, VS Code, JetBrains y la aplicación Claude Desktop.

---

## El bucle agéntico

Claude Code se explica mejor a través del bucle agéntico:

1. **Ingresas un prompt** en Claude Code.
2. **Reúne el contexto** que necesita interactuando con el modelo, que devuelve texto o una llamada a herramienta que Claude Code puede ejecutar.
3. **Toma acción** — por ejemplo, editando un archivo o ejecutando un comando.
4. **Verifica los resultados** y determina si logran lo que tu prompt se propuso hacer.

Si lo logran, Claude termina y espera el siguiente prompt. Si no lo logran, vuelve al inicio del bucle e intenta de nuevo hasta que los resultados sean completos y verificables.

A lo largo de este bucle, puedes agregar contexto, interrumpir o guiar al modelo para ayudarlo a avanzar hacia tu objetivo.

> **Diagrama del bucle agéntico:** Tu prompt fluye hacia el bucle de *Reunir contexto*, *Tomar acción* y *Verificar resultados*, con la capacidad de interrumpir, guiar o agregar contexto en cualquier momento

---

## Contexto

Claude tiene una ventana de contexto que determina cuánto de tu conversación, contenido de archivos, salidas de comandos y más puede almacenar y referenciar. Una vez que alcanzar ese límite, Claude Code compacta tu conversación — determinando automáticamente qué puede eliminar o resumir para reducir la ventana de contexto a un tamaño utilizable.

---

## Herramientas

Las herramientas son la columna vertebral de cómo funcionan los agentes. La mayoría de los asistentes de IA simplemente toman texto como entrada y devuelven texto como salida.

Las herramientas permiten que Claude Code determine cuándo ejecutar código para acercarse a completar una tarea. Esto podría ser:

- Una herramienta de lectura de archivos
- Una herramienta de búsqueda web
- Cualquier otra cantidad de capacidades

> Claude Code usa comprensión semántica para determinar cuándo llamar a una herramienta y cómo usar la salida.

---

## Permisos

Claude Code tiene varios modos de permisos:

| Modo | Descripción |
|------|-------------|
| **Manual** (predeterminado) | Claude pide permiso explícito antes de editar un archivo o ejecutar un comando de shell |
| **Aceptación automática** | Los archivos se editan sin preguntar, pero los comandos aún requieren aprobación |
| **Modo de planificación** | Usa herramientas de solo lectura para compilar un plan de acción antes de comenzar cualquier trabajo |

> Claude Code pidiendo permiso antes de ejecutar un comando bash

Todo esto se puede configurar en tu archivo de configuración. Ten cuidado al omitir permisos — darle a Claude Code total libertad para ejecutar comandos significa que un error podría ser más difícil de detectar antes de que ocurra.

---

> **Resumen:** Claude Code combina varios conceptos agénticos: un bucle agéntico, una ventana de contexto gestionada, herramientas y permisos configurables — todo dentro de tu terminal. Puede leer tu base de código, tomar acción y verificar su propio trabajo. Eso es lo que lo hace fundamentalmente diferente de una ventana de chat.

---

## Auto-Aceptar vs. Manual

Puedes elegir si Claude acepta automáticamente cada cambio de archivo que sugiere, o si pide tu permiso explícito cada vez. Presiona **Shift + Tab** para alternar entre modos.

### Modo manual

Claude pide permiso cada vez que quiere editar un archivo o ejecutar un comando.

### Modo de auto-aceptación

Las ediciones de archivos se aprueban automáticamente, pero los comandos aún requieren tu permiso.

> No hay una respuesta correcta o incorrecta — es lo que te resulte más cómodo.

> Claude Code en modo de auto-aceptación, leyendo archivos y trabajando en una tarea

---

## Modo Plan

Dentro del menú Shift + Tab está el **Modo Plan**. El modo plan toma tu prompt y usa herramientas de solo lectura para analizar tu base de código e investigar tu implementación sugerida. Hará preguntas aclaratorias en el camino, y luego devolverá un plan detallado que puede ejecutar.

> El modo plan es excelente para planificar cambios complejos o hacer una revisión de código segura. Muchas veces le pedirás a Claude que maneje implementaciones de varios pasos hacia una funcionalidad, y es exactamente ahí donde el Modo Plan destaca.

> Claude Code con el modo plan activado, mostrando el indicador de la barra de estado

---

## Ejemplo: Agregar un Interruptor de Modo Oscuro

Repasemos un ejemplo. Supongamos que tienes una aplicación que necesita un interruptor de modo oscuro.

1. Abre el directorio raíz de tu proyecto y ejecuta `claude`.
2. Presiona **Shift + Tab** un par de veces para entrar en el Modo Plan.
3. Luego escribe un prompt como:

```
Mi aplicación necesita un modo oscuro implementado en toda la aplicación. ¿Puedes crear un interruptor en el encabezado que permita a un usuario alternar entre el modo claro y el modo oscuro? Necesito que encuentres un buen color de contraste que funcione según mi tema claro existente.
```

> Ingresando el prompt de modo oscuro en Claude Code con el modo plan habilitado

**Deja que Claude lo planifique.** Después de revisar el plan, si se ve bien, acéptalo y deja que Claude te pida aprobación en cada paso. Al final, puedes ver exactamente qué hizo Claude y cómo llegó a sus conclusiones.

---

> **Resumen:** Cuando uses Claude Code, intenta ser lo más descriptivo posible con tu prompt. Si quieres mantenerte al tanto en cada paso, puedes hacerlo. Usa el Modo Plan para dejar que Claude profundice en los detalles de lo que quieres lograr antes de ejecutar cualquier código.