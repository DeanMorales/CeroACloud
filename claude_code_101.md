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

---

## El flujo de trabajo: Explorar → Planificar → Codificar → Confirmar

### Explorar y Planificar

La forma más rápida de manejar estos primeros dos pasos es con el **Modo de Planificación**. En el modo de planificación, Claude no puede editar archivos; solo lee archivos para recopilar información sobre cómo abordará la implementación.

Para entrar en el modo de planificación, presiona **Shift + Tab** hasta que veas "Plan Mode" debajo del campo de texto. Luego escribe una indicación como:

> Barra de estado de Claude Code mostrando el modo de planificación activado con shift+tab para alternar

```
Necesito agregar conversión a WebP a nuestro pipeline de carga de imágenes. Averigua en qué parte del pipeline debería ocurrir, si necesitamos nuevas dependencias y cómo abordarlo.
```

Claude leerá los archivos relevantes, ejecutará algunas búsquedas web y te dará un plan de acción. Revísalo y decide si cumple con tus criterios. Si no, pídele que revise áreas específicas.

> Claude Code presentando el plan con opciones para aprobar, revisar áreas o hacer preguntas

Este es el mejor lugar para corregir el rumbo porque es antes de que se escriba cualquier código. También puedes ejecutar el subagente de exploración sin estar en el modo de planificación si solo quieres un resumen general de tu base de código sin intención de hacer cambios después.

### Codificar

Una vez que el plan se vea bien, selecciona "aprobar" para aceptarlo y dejar que Claude trabaje en la lista de elementos. Puedes elegir si Claude acepta automáticamente las ediciones de archivos o te pregunta cada vez.

Claude hará todo lo posible para solucionar problemas antes de considerar el plan "terminado", pero a veces necesitarás intervenir. Este es el beneficio de trabajar con el Modo de Planificación: después de la ejecución, también tienes el contexto de cómo llegaste a los resultados, lo cual ayuda a guiar las próximas decisiones de Claude.

**Algunos consejos para hacer más fluida la fase de codificación:**

| Consejo | Descripción |
|---------|-------------|
| **Define un criterio de éxito** | Para que Claude tenga confianza en sus resultados, necesita tener claro cómo se ve "correcto". Haz esto explícito al escribir tu plan. |
| **Agrega herramientas** | Las herramientas que ayudan a Claude a lograr sus objetivos eliminan mucho de ida y vuelta. Por ejemplo, si estás construyendo interfaces web, instala la extensión Claude in Chrome para que Claude Code pueda controlar una pestaña del navegador y probar la interfaz directamente. |
| **Incluye un conjunto de pruebas** | Dale a Claude un conjunto de pruebas contra el cual pueda validar continuamente. Claude incluso puede escribir pruebas por ti. Antes de entregar esto, asegúrate de que las pruebas sean una fuente confiable de verdad para evitar falsos positivos. |

> La página de la extensión Claude in Chrome en la Chrome Web Store

> **Consejo rápido:** Si notas que Claude sigue encontrando los mismos problemas, pídele que guarde la solución en su archivo `CLAUDE.md`.

### Confirmar

Una vez que hayas probado los cambios tú mismo y estés satisfecho con los resultados, es momento de subir tu código. Antes de confirmar, ejecuta un subagente revisor de código para que revise tu trabajo. Un subagente aporta una mirada fresca a la base de código; no carga con el sesgo que el agente principal podría tener de la sesión.

> Un subagente revisor de código ejecutándose en Claude Code, leyendo archivos y revisando cambios recientes

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

> Diagrama que muestra la ventana de contexto como una cuadrícula de tokens — algunos ocupados, la mayoría disponibles

### Qué sucede cuando el contexto se llena

Cuando te acercas al límite, la ventana de contexto se compacta automáticamente. La compactación resume los detalles importantes y elimina los resultados de llamadas a herramientas innecesarios para liberar espacio. Ten en cuenta que este proceso puede potencialmente perder detalles.

> Claude Code mostrando 'Compactando conversación...' mientras resume el contexto

> Claude Code mostrando un resumen compacto de la conversación anterior, incluyendo conceptos técnicos clave y archivos

### Comandos

Puedes ejecutar la compactación manualmente con el comando `/compact`. Esto compacta todo hasta ese punto. Es útil cuando quieres liberar espacio de contexto mientras mantienes un recuerdo de lo que trabajaste previamente.

> El comando /compact en el menú de autocompletado de Claude Code

Si quieres comenzar completamente desde cero sin memoria de la sesión anterior, ejecuta `/clear`. Esto elimina todo.

> Ejecutando /clear en Claude Code para comenzar una sesión nueva

Para verificar el estado de tu contexto, ejecuta el comando `/context`. Obtendrás una visión general de alto nivel del tamaño de tu contexto, las categorías que ocupan más espacio, y un gráfico visual que muestra el desglose.

> Salida del comando /context mostrando el desglose del uso de contexto con un gráfico de barras visual

### Cuándo usar cuál

**Una regla general:**

| Comando | Cuándo usarlo |
|---------|---------------|
| `/compact` | Cuando estés trabajando en una función específica y te estés acercando al límite de contexto pero necesites continuar. Mantener el contexto relevante a tu función actual es importante. |
| `/clear` | Cuando quieras comenzar una nueva función. No quieres que la conversación anterior introduzca sesgo en algo nuevo. |

> Para las cosas que quieres que Claude recuerde entre sesiones, colócalas en tu archivo `CLAUDE.md` para que no tenga que redescubrirlas desde cero.

> Un archivo CLAUDE.md con comandos, notas importantes y secciones de arquitectura

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