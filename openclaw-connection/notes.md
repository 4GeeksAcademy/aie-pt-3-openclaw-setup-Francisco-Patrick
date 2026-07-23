* **1. Configuraciones**
La decisión de usar Discord vs Telegram es, meramente, personal: No uso Telegram. Sin embargo, Discord es una aplicación que uso, prácticamente, todos los días y con el que estoy muy familiarizado. Y me resulta más cercano que Telegram.

Para su configuración tuve que acceder a Discord Developer Portal y crear un nuevo bot desde ahí. Crear el token con permisos de Lectura/Ver canales, Leer historial y escribir mensajes.
Invitar el bot a un servidor para poder iniciar un chat con el bot y obtener el Pairing Code.

Sin complicaciones.

* **2. MCP**
Durante este proceso tuve problemas iniciales con activar el servidor mcporter. El problema residía en que no obtenía conexión con el servidor a través del link.

*¿Cómo lo arreglé?*
- Si bien no estoy seguro del cómo, lo que hice fue reinstalar dependencias, realizar la configuración otra vez y ahí ya conseguí que tuviera conexión con  Composio.

Después de esto, OpenClaw tenía problemas con usar el mcporter, intentando o ignorando su configuración y trataba de usar el CLI de Composio.

*¿Cómo lo arreglé?*
- Especificando cómo debía proceder. Consulté con GEMINI sobre los errores que me estaba devolviendo el Asistente y me proporcionó una explicación sobre qué ocurría. Reescribí un prompt para que se ajustara a usar mcporter. Un detalle de ejecutar "mcporter list composio --schema" para que entendiera que tools tenía disponible.
El siguiente problema vino con la ejecución de estructuras json en su forma cruda (raw). Tuve que especificarle cómo debía usaarlo. Y para evitar futuros errores, le indiqué se actualizara para que no volviera a ocurrir.
