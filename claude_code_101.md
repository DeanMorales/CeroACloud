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

---

## Modo Plan

Dentro del menú Shift + Tab está el **Modo Plan**. El modo plan toma tu prompt y usa herramientas de solo lectura para analizar tu base de código e investigar tu implementación sugerida. Hará preguntas aclaratorias en el camino, y luego devolverá un plan detallado que puede ejecutar.

> El modo plan es excelente para planificar cambios complejos o hacer una revisión de código segura. Muchas veces le pedirás a Claude que maneje implementaciones de varios pasos hacia una funcionalidad, y es exactamente ahí donde el Modo Plan destaca.

---

## Ejemplo: Agregar un Interruptor de Modo Oscuro

Repasemos un ejemplo. Supongamos que tienes una aplicación que necesita un interruptor de modo oscuro.

1. Abre el directorio raíz de tu proyecto y ejecuta `claude`.
2. Presiona **Shift + Tab** un par de veces para entrar en el Modo Plan.
3. Luego escribe un prompt como:

```
Mi aplicación necesita un modo oscuro implementado en toda la aplicación. ¿Puedes crear un interruptor en el encabezado que permita a un usuario alternar entre el modo claro y el modo oscuro? Necesito que encuentres un buen color de contraste que funcione según mi tema claro existente.
```

**Deja que Claude lo planifique.** Después de revisar el plan, si se ve bien, acéptalo y deja que Claude te pida aprobación en cada paso. Al final, puedes ver exactamente qué hizo Claude y cómo llegó a sus conclusiones.

---

> **Resumen:** Cuando uses Claude Code, intenta ser lo más descriptivo posible con tu prompt. Si quieres mantenerte al tanto en cada paso, puedes hacerlo. Usa el Modo Plan para dejar que Claude profundice en los detalles de lo que quieres lograr antes de ejecutar cualquier código.

---

## El flujo de trabajo: Explorar → Planificar → Codificar → Confirmar

### Explorar y Planificar

La forma más rápida de manejar estos primeros dos pasos es con el **Modo de Planificación**. En el modo de planificación, Claude no puede editar archivos; solo lee archivos para搜集 información sobre cómo abordará la implementación.

Para entrar en el modo de planificación, presiona **Shift + Tab** hasta que veas "Plan Mode" debajo del campo de texto. Luego escribe una indicación como:

```
Necesito agregar conversión a WebP a nuestro pipeline de carga de imágenes. Averigua en qué parte del pipeline debería ocurrir, si necesitamos nuevas dependencias y cómo abordarlo.
```

Claude leerá los archivos relevantes, ejecutará algunas búsquedas web y te dará un plan de acción. Revísalo y decide si cumple con tus criterios. Si no, pídele que revise áreas específicas.

Este es el mejor lugar para corregir el rumbo porque es antes de que se escriba cualquier código. También puedes ejecutar el subagente de exploración sin estar en el modo de planificación si solo quieres un resumen general de tu base de código sin intención de hacer cambios después.

### Codificar

Una vez que el plan se vea bien, selecciona "aprobar" para aceptarlo y dejar que Claude trabaje en la lista de elementos. Puedes elegir si Claude acepta automáticamente las ediciones de archivos o te pregunta cada vez.

Claude hará todo lo posible para solucionar problemas antes de considerar el plan "terminado", pero a veces necesitarás intervenir. Este es el beneficio de trabajar con el Modo de Planificación: después de la ejecución, también tienes el contexto de cómo llegaste a los resultados, lo cual ayuda a guiar las próximas decisiones de Claude.

**Algunos consejos para hacer más fluida la fase de codificación:**

| Consejo | Descripción |
|---------|-------------|
| **Define un criterio de éxito** | Para que Claude tenga confianza en sus resultados, necesita tener claro cómo se ve "correcto". Haz esto explícito al escribir tu plan. |
| **Agrega herramientas** | Las herramientas que ayudan a Claude a lograr sus objetivos eliminan mucho de ida y vuelta. |
| **Incluye un conjunto de pruebas** | Dale a Claude un conjunto de pruebas contra el cual pueda validar continuamente. |

> **Consejo rápido:** Si notas que Claude sigue encontrando los mismos problemas, pídele que guarde la solución en su archivo `CLAUDE.md`.

### Confirmar

Una vez que hayas probado los cambios tú mismo y estés satisfecho con los resultados, es momento de subir tu código. Antes de confirmar, ejecuta un subagente revisor de código para que revise tu trabajo. Un subagente aporta una mirada fresca a la base de código; no carga con el sesgo que el agente principal podría tener de la sesión.

Luego pídele a Claude que genere un mensaje de confirmación en tu estilo. Repite el proceso.

---

### Resumen

Para ser efectivo con Claude Code, sigue el flujo de trabajo **Explorar, Planificar, Codificar y Confirmar**:

| Fase | Descripción |
|------|-------------|
| **Explorar** | Le da a Claude el contexto relevante que necesita para tu proyecto. |
| **Planificar** | Crea un plan de acción que Claude usa para medir el éxito. |
| **Codificar** | Es el ir y venir entre tú y Claude antes de decidir el resultado final. |
| **Confirmar** | Te ayuda a revisar y subir tu código para que puedas comenzar con tu próxima función. |

---

## Gestión del contexto

### ¿Qué es la ventana de contexto?

Piensa en la ventana de contexto como la cantidad de espacio que Claude puede retener en su memoria. Cada vez que ingresas un prompt, Claude lee un archivo, ejecuta una llamada a una herramienta o recibe el resultado de una llamada a una herramienta, todo eso se va agregando a la ventana de contexto. Dado que hay una cantidad finita de espacio, se vuelve importante optimizar cómo lo usas.

### Qué sucede cuando el contexto se llena

Cuando te acercas al límite, la ventana de contexto se compacta automáticamente. La compactación resume los detalles importantes y elimina los resultados de llamadas a herramientas innecesarios para liberar espacio. Ten en cuenta que este proceso puede potencialmente perder detalles.

### Comandos

Puedes ejecutar la compactación manualmente con el comando `/compact`. Esto compacta todo hasta ese punto. Es útil cuando quieres liberar espacio de contexto mientras mantienes un recuerdo de lo que trabajaste previamente.

Si quieres comenzar completamente desde cero sin memoria de la sesión anterior, ejecuta `/clear`. Esto elimina todo.

Para verificar el estado de tu contexto, ejecuta el comando `/context`. Obtendrás una visión general de alto nivel del tamaño de tu contexto, las categorías que ocupan más espacio, y un gráfico visual que muestra el desglose.

### Cuándo usar cuál

**Una regla general:**

| Comando | Cuándo usarlo |
|---------|---------------|
| `/compact` | Cuando estés trabajando en una función específica y te estés acercando al límite de contexto pero necesites continuar. |
| `/clear` | Cuando quieras comenzar una nueva función. No quieres que la conversación anterior introduzca sesgo en algo nuevo. |

> Para las cosas que quieres que Claude recuerde entre sesiones, colócalas en tu archivo `CLAUDE.md` para que no tenga que redescubrirlas desde cero.

### Consejos para ahorrar espacio de contexto

**Sé específico.** Un prompt vago puede parecer más pequeño, pero en realidad cuesta más contexto a largo plazo. Sin instrucciones claras, Claude se ve forzado a explorar más tu base de código y hacer su propio razonamiento — lo cual ocupa mucho más espacio de contexto que un prompt detallado.

**Gestiona tus servidores MCP.** Los servidores MCP cargan todas sus herramientas disponibles en el contexto por defecto, incluso cuando no las estás usando. Si tienes servidores configurados para cosas no relacionadas con el proyecto actual, considera desactivarlos. También puedes probar las "Skills", que funcionan de manera similar a los servidores MCP pero no cargan todo en el contexto de antemano.

**Usa subagentes.** Los subagentes se ejecutan en paralelo con tu agente principal pero tienen una ventana de contexto completamente separada. Para tareas en las que solo necesitas la respuesta — como "¿dónde están ubicados los endpoints de autenticación?" — un subagente hace el trabajo y devuelve solo un resumen a tu agente principal, manteniendo limpio tu contexto principal.

---

> **Resumen:** Gestionar el contexto dentro de Claude Code es crucial. Usa `/compact` para resumir sesiones largas y `/clear` para comenzar de nuevo. Para usar tu ventana de contexto de manera efectiva: sé específico con tus prompts, verifica qué está consumiendo tu contexto actual, y usa subagentes para delegar tareas donde solo necesitas el resultado.

---

## Revisión de código

### Revisar con un Subagente

Antes de enviar un PR, pídele a Claude que use un subagente para revisar tus cambios. El subagente se ejecuta en su propia ventana de contexto con una mirada fresca: no carga con el sesgo del agente principal que acaba de pasar la sesión escribiendo el código.

Al crear un subagente revisor de código, restríngelo a herramientas de solo lectura. Un revisor debe señalar problemas, no editar archivos. Registra la configuración del subagente en tu repositorio para que todo tu equipo use el mismo revisor.

### La Skill /commit-push-pr

La skill `/commit-push-pr` gestiona el commit, el push y la creación del PR todo en un solo paso. En lugar de hacer cada cosa manualmente, simplemente ejecuta la skill y Claude se encarga de ello.

Si tienes un servidor MCP de Slack configurado con canales listados en tu `CLAUDE.md`, publicará automáticamente el enlace del PR en el canal de tu equipo.

### Vinculación de sesiones con --from-pr

Cuando Claude crea un PR mediante `gh pr create`, la sesión se vincula automáticamente a ese PR. Si necesitas volver a ella más tarde —quizás para abordar comentarios de revisión o corregir una compilación fallida— ejecuta:

```bash
claude --from-pr <PR_NUMBER>
```

Esto retoma justo donde lo dejaste.

---

### Resumen

- Usa un subagente para obtener una revisión de código imparcial antes de hacer push.
- Usa `/commit-push-pr` para gestionar todo el flujo de commit a PR en un solo paso.
- Usa `--from-pr` para reanudar el trabajo en un PR más tarde.

Son funciones pequeñas, pero eliminan mucha fricción de tu flujo de trabajo diario.

---

## El archivo CLAUDE.md

### El problema que resuelve

Cuando abres Claude Code sin un archivo CLAUDE.md, comienza desde cero cada vez. Tiene que volver a explorar tu base de código,averigar qué dependencias se necesitan y entender qué funciones ya están implementadas. A veces hace suposiciones, lo que dificulta guiar a Claude en la dirección correcta.

**CLAUDE.md** resuelve esto. Es un archivo Markdown que agregas a la raíz de tu proyecto, y Claude Code lo lee automáticamente cada vez que inicias una sesión. Piénsalo como un script de incorporación para tu base de código. El contenido del archivo CLAUDE.md se añade a tu prompt.

### Un ejemplo

Así es como se ve un archivo CLAUDE.md típico:

```markdown
# Project

This is a Next.js 15 app using the App Router, Tailwind, and Drizzle ORM.

# Commands
- Dev server: `pnpm dev`
- Run tests: `pnpm test`
- Lint: `pnpm lint`

# Code Style
- Use 2-space indentation
- Prefer named exports
- All API routes go in app/api/
- Use server actions instead of API routes where possible
```

Es sencillo. Ahora, si le pides a Claude Code que cree un componente de React, ya sabe que debe usar Tailwind para los estilos y seguir tus convenciones de código.

### CLAUDE.md es para equipos

Puedes (y deberías) confirmar tu CLAUDE.md en el control de versiones para que tu equipo se beneficie de él. De hecho, existe una jerarquía de archivos de memoria según para quién sean:

| Tipo | Ubicación | Alcance |
|------|-----------|---------|
| **Proyecto** | Directorio raíz del proyecto | Se comparte con el equipo |
| **Usuario** | Carpeta de configuración | Solo para ti, se aplica en todos tus proyectos |

### Consejos

**Guarda las correcciones en la memoria.** Si te encuentras corrigiendo a Claude repetidamente — como decirle que siempre use server actions en lugar de rutas de API — pídele explícitamente a Claude que guarde esa regla en la memoria. La próxima vez que abras el proyecto, lo sabrá.

**Haz referencia a la documentación del proyecto.** Si tienes documentación en tu proyecto que quieres que Claude consulte, usa el símbolo `@` con la ruta del archivo:

```markdown
Please read if you need more info: @README.md
```

**Empieza sin uno.** Recomendamos comenzar un proyecto sin un archivo CLAUDE.md para que puedas ver dónde constantemente tienes que corregir el rumbo del modelo. Esto mantiene tu CLAUDE.md compacto y enfocado solo en la información necesaria. Cuando estés listo, ejecuta `/init` para que Claude genere uno por ti.

---

> **Resumen:** La diferencia entre una sesión frustrante de Claude Code y una productiva a menudo se reduce al contexto — y el archivo CLAUDE.md es cómo proporcionas ese contexto. Comienza con tu stack, tus preferencias y tus comandos, y luego construye a partir de ahí sobre la marcha.

---

## Subagentes

### Cómo funciona

Gestionar el contexto en Claude Code es importante. Gran parte de la ventana de contexto se consume con cosas como llamadas a herramientas que exploran tu base de código o ejecutan búsquedas web para investigación. Lo que Claude descubre durante esa exploración no siempre es relevante para la función principal que estás desarrollando.

Aquí es donde entran los **subagentes**. Claude genera un subagente para manejar una tarea como "explora esta base de código por mí". El subagente se ejecuta en paralelo con su propia ventana de contexto, realiza todo el trabajo de exploración y, una vez terminado, resume sus hallazgos y devuelve ese resumen a Claude.

El resultado: obtienes la respuesta que buscabas, sin que todo el recorrido necesario para llegar a ella sature tu contexto principal.

### Creando tu propio subagente

Los subagentes se definen en archivos Markdown con frontmatter YAML. La forma más fácil de empezar es dejar que Claude genere uno por ti. Ejecuta:

```
/agents
```

Luego selecciona "Create new agent" (Crear nuevo agente). Pasarás por pasos que incluyen elegir el alcance del agente, definir su propósito, seleccionar las herramientas a las que tiene acceso e incluso elegir un color para él.

Claude generará un nombre, una descripción y un prompt para el subagente. Esto también le indica a Claude cuándo llamar al subagente según los prompts que le das.

### Personalización adicional

Los subagentes se pueden personalizar aún más. Aquí hay algunos aspectos destacados:

| Característica | Descripción |
|----------------|-------------|
| **Memoria persistente** | Permite que tu subagente retenga memoria entre conversaciones. Ideal si lo usas de forma constante en los mismos proyectos. |
| **Precarga de skills** | Agrega la clave `skills` y lista las habilidades por nombre. Se carga la habilidad completa en el contexto. |

---

> **Resumen:** Mantener limpia tu ventana de contexto es una de las mejores formas de seguir siendo productivo con Claude Code. Con los subagentes, puedes ejecutar un agente en segundo plano para encargarse del trabajo pesado y devolver solo la respuesta a tu ventana de contexto principal.

---

## Skills

Cada vez que le explicas a Claude los estándares de codificación de tu equipo, te estás repetiendo. Cada revisión de PR, vuelves a describir cómo quieres que se structure el feedback. Cada mensaje de commit, le recuerdas a Claude tu formato preferido. **Las skills resuelven esto.**

Una **skill** es un archivo Markdown que le enseña a Claude cómo hacer algo una vez, y Claude aplica ese conocimiento automáticamente cuando es relevante. Las skills son carpetas de instrucciones, scripts y recursos que los agentes pueden descubrir y usar para hacer las cosas de manera más precisa y eficiente.

Con Claude Code, tenemos el archivo **SKILL.md**. La descripción es cómo Claude decide si debe usar la skill. Cuando le pides a Claude que revise este PR, compara tu solicitud con las descripciones de skills disponibles y encuentra esta. Claude lee tu solicitud, la compara con todas las descripciones de skills disponibles y activa las que coinciden.

### Dónde guardar las skills

Puedes guardar las skills en algunos lugares dependiendo de quién las necesite:

| Tipo | Ubicación | Descripción |
|------|-----------|-------------|
| **Personales** | `.claude/skills` en tu directorio home | Te siguen a todos tus proyectos. Preferencias personales, estilo de mensajes de commit, formato de documentación. |
| **De proyecto** | `.claude/skills` en el raíz del repositorio | Cualquiera que clone el repositorio obtiene estas skills automáticamente. Estándares del equipo, guías de marca, colores preferidos. |

### Por qué skills y no otras cosas?

Claude Code tiene varias formas de personalizar el comportamiento. Las skills son únicas porque son automáticas y específicas para tareas.

- **CLAUDE.md** se carga en cada conversación. Si quieres que Claude siempre use TypeScript en modo estricto, ponlo en tu CLAUDE.md.
- **Skills** se cargan bajo demanda cuando coinciden con tu solicitud. Solo carga el nombre y la descripción, así que no llena toda tu ventana de contexto.

Los comandos de barra (/commands) requieren que los escribas, las skills no. Claude las aplica cuando reconoce la situación.

---

> **Resumen:** Si te encuentras explicándole lo mismo a Claude repetidamente, eso es una skill que está esperando ser escrita. Las skills son ideales para conocimiento especializado que aplica a tareas específicas.

---

## MCP

Gran parte de tu contexto vive fuera de tu base de código — en bases de datos, aplicaciones de productividad o repositorios públicos. **MCP** cierra esa brecha.

### ¿Qué puedes hacer con esto?

Primero, es importante entender el concepto de "herramientas" en la IA agéntica. Las herramientas le dan a agentes como Claude Code la capacidad de realizar acciones que les ayudan a completar tareas de manera más efectiva. Esto es diferente de la IA típica, donde simplemente obtienes una respuesta de texto.

Por ejemplo:

- Si tu equipo usa **Linear** para la gestión de proyectos, puedes agregar un servidor MCP de Linear para traer los detalles de tus incidencias específicas.
- Si necesitas documentación actualizada para una dependencia, un servidor MCP de documentación como **Context7** puede proporcionársela a Claude Code.

### Agregar un Servidor MCP

Puedes agregar servidores MCP con el comando:

```bash
claude mcp add
```

Hay dos tipos principales:

| Tipo | Descripción |
|------|-------------|
| **HTTP** | Para servicios remotos. Alojado por el proveedor del servicio y se conecta a través de la red. |
| **Stdio** | Para procesos locales que se ejecutan en tu máquina. |

Puedes gestionar tus servidores con `/mcp` dentro de una sesión de Claude Code para ver qué está conectado, verificar el estado y deshabilitar los servidores que no necesitas.

### Alcance de los Servidores

Los servidores MCP pueden tener alcance de tres maneras:

| Alcance | Descripción |
|---------|-------------|
| **Local** | Solo disponible en el proyecto actual, únicamente para ti. |
| **Usuario** | Disponible en todos tus proyectos. |
| **Proyecto** | Usa un archivo `.mcp.json` que registras en el control de versiones para que cualquiera en la base de código obtenga automáticamente los mismos servidores exactos. |

### Costos de Contexto

Los servidores MCP agregan definiciones de herramientas a tu ventana de contexto — incluso cuando no los estás usando activamente. Si tienes muchos servidores configurados, esto consume tu contexto disponible.

> Ejecuta `/mcp` para ver qué está conectado y deshabilitar cualquier cosa que no estés usando activamente.

Si una herramienta tiene un equivalente de CLI (como `gh` para GitHub o `aws` para AWS), la CLI es más eficiente en cuanto a contexto porque no agrega definiciones de herramientas persistentes.

También podrías beneficiarte de usar una **Skill** en su lugar. Una Skill tiene un nombre y una descripción cargados en el contexto, y Claude solo carga el contenido completo de la skill cuando determina que necesita usarla.

Si tus herramientas MCP superan el 10% de tu ventana de contexto, Claude Code cambia automáticamente al modo de búsqueda de herramientas, que descubre las herramientas correctas según sea necesario.

---

> **Resumen:** MCP conecta Claude Code con tus herramientas y fuentes de datos externas. Agrega servidores con `claude mcp add`. Dales alcance a tu proyecto con `.mcp.json` para que tu equipo los obtenga automáticamente. Y mantén un ojo en el uso de contexto deshabilitando los servidores que no estés usando activamente.

---

## Hooks

### Por qué usar Hooks

Puedes decirle a Claude en tu CLAUDE.md que ejecute Prettier después de cada edición de archivo. La mayoría de las veces lo hará. Pero a veces no. Un **hook** hace que suceda cada vez, sin excepciones.

**Casos de uso comunes:**

- Formateo automático después de ediciones de archivos
- Registro de todos los comandos ejecutados para cumplimiento normativo
- Bloqueo de operaciones peligrosas como modificar archivos de producción
- Envío de notificaciones cuando Claude termina una tarea

### Cómo funcionan

Los hooks se configuran en tu `settings.json`. Eliges un evento, opcionalmente estableces un matcher para las herramientas a las que se aplica, y proporcionas un comando para ejecutar.

**Algunos de los eventos más comunes:**

| Evento | Descripción |
|--------|-------------|
| **PreToolUse** | Se ejecuta antes de una llamada a una herramienta |
| **PostToolUse** | Se ejecuta después de que se completa una llamada a una herramienta |
| **UserPromptSubmit** | Se ejecuta cuando envías un prompt, antes de que Claude lo procese |
| **Stop** | Se ejecuta cuando Claude termina de responder |
| **Notification** | Se ejecuta cuando Claude envía una notificación |

Los configuras a través del comando `/hooks` dentro de Claude Code, o editando `settings.json` directamente.

### Un ejemplo práctico

El hook más común: formateo automático después de ediciones. Configura un hook PostToolUse con un matcher de `Edit|MultiEdit|Write` para que se active cada vez que Claude modifique un archivo. El comando verifica la extensión del archivo y ejecuta el formateador apropiado — Prettier para TypeScript, gofmt para Go, lo que sea que use tu proyecto.

### Bloqueo con PreToolUse

Los hooks de PreToolUse pueden bloquear llamadas a herramientas antes de que se ejecuten. Tu hook recibe el nombre de la herramienta y la entrada como JSON en stdin. El código de salida determina el comportamiento:

| Código de salida | Comportamiento |
|------------------|----------------|
| **0** | Proceder normalmente |
| **2** | Bloquear la acción. El mensaje de stderr se devuelve a Claude como retroalimentación |
| **Otro** | Error no bloqueante que se muestra pero no detiene nada |

Así es como se aplican reglas estrictas:

- Bloquea escrituras en un directorio de configuración de producción
- Bloquea comandos bash que contengan `rm -rf`
- Bloquea commits a main

### Compartir Hooks con tu equipo

Los hooks configurados en `.claude/settings.json` son a nivel de proyecto y pueden incluirse en tu repositorio. Esto significa que todo tu equipo obtiene los mismos hooks automáticamente.

> Usa la variable de entorno `CLAUDE_PROJECT_DIR` en tus comandos para referenciar scripts almacenados en tu proyecto, de modo que funcionen independientemente del directorio de trabajo actual de Claude.

---

> **Resumen:** Los hooks te dan control determinista sobre el comportamiento de Claude Code. Usa PostToolUse para formateo automático y registro. Usa PreToolUse para bloquear operaciones peligrosas. Configúralos con `/hooks` o en settings.json. Y agrégalos a tu repositorio para que tu equipo también los obtenga.

**Si algo necesita suceder cada vez sin fallar, no lo pongas en un prompt. Ponlo en un hook.**