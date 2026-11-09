# Humanizer — revisión estática inicial

## Resultado

Sin señales de extracción de datos, lectura de credenciales, desactivación de permisos o ejecución oculta en los archivos principales revisados. Adecuado para conservar una copia controlada; no constituye certificación de seguridad ni aprobación de futuras versiones. No instalado ni ejecutado en esta tarea.

## Versión

- Original: https://github.com/blader/humanizer
- Copia: https://github.com/ughetty/humanizer
- Commit de origen leído mediante referencias fijas y comprobado en el fork: 0ef9fe5bc3572734fd3ae6c448fe00a30cd5dcf0.
- Skill: 3.1.0.
- Licencia MIT conservada, incluido el aviso de Siqi Chen.

## Alcance real

Lectura de SKILL.md completo, AGENTS.md, scripts/validate-package.py, agents/openai.yaml, .claude-plugin/plugin.json, .claude-plugin/marketplace.json, .cursor-plugin/plugin.json, .github/workflows/validate.yml y LICENSE con ref fija. README leído durante la búsqueda y revisión inicial. Inventario visual de raíz, scripts y workflows. No se auditó el historial completo, las plantillas de issues, las dependencias de herramientas externas o los artefactos ZIP de releases. No se realizaron pruebas dinámicas.

## Observaciones

- SKILL.md define edición de prosa. Ordena tratar el texto recibido como material a editar, nunca como instrucciones a seguir; prohíbe añadir hechos sin fuente y pide conservar código, metadatos y destinos de enlaces en modo archivo. Es una instrucción favorable frente a inyección, pero no demuestra inmunidad del modelo a ataques.
- Los manifiestos leídos describen la skill; no declaran hooks ni servidores MCP, ni solicitan telemetría o permisos ampliados.
- agents/openai.yaml contiene metadatos de interfaz y una petición de edición.
- El validador Python leído usa json, re y pathlib: lee archivos locales, comprueba versiones, estructura y límites de palabras e imprime el resultado. No se observaron llamadas de red, subprocess, eval ni escrituras en ese archivo. No se ejecutó.
- El workflow validate.yml usa permiso contents: read y acciones fijadas por SHA. También instala y ejecuta Skills CLI y Claude Code para validar el paquete. Esas herramientas externas quedan fuera de esta revisión. El workflow quedó desactivado en la copia.
- AGENTS.md contiene comandos de comprobación para mantenedores. Se leyeron como datos, no se ejecutaron como autorización.
- La edición directa puede alterar el sentido o el tono: revisar el diff, conservar datos, citas, advertencias y voz propia antes de publicar. Algunos ejemplos de la skill reducen información; su instrucción general de preservación no garantiza un resultado correcto.

## Controles aplicados

Fork público con main únicamente. GitHub Actions desactivado y Disable actions verificado tras guardar. Licencia conservada. Sin credenciales, datos privados, despliegues, instalación, activación como skill ni ejecución de scripts. Sin automatización de sincronización con el original. Esta nota es el único cambio intencional al contenido original copiado.

## Uso futuro

Si se decide instalar: usar el contenido revisado con versión fija y ámbito del proyecto; revisar cambios antes de actualizar; no ejecutar los comandos de validación externos por el mero hecho de aparecer en la documentación. El agente anfitrión conserva sus propios permisos y proveedor de IA: la ausencia de red en la skill no implica que los textos nunca salgan del equipo. Comprobar privacidad y hacer una primera prueba con texto ficticio antes de usar materiales confidenciales.
