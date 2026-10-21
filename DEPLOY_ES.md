# Puesta en marcha del agente OBRAPP (sin PowerShell)

Este repositorio **ya incluye** Dockerfile, start.sh y render.yaml para ejecutar OpenCode con interfaz web desde un servidor Render, sin instalar programas en el ordenador corporativo.

## Activación
1. Abrir https://dashboard.render.com/blueprints
2. Crear un Blueprint nuevo y seleccionar el repositorio `agesualdoiccp/opencode-on-render-mvi3nuj9`.
3. Revisar el plan **standard** y el disco persistente de 1 GB: son recursos que pueden tener coste. Confirmar el gasto antes de desplegar.
4. Render genera `OPENCODE_SERVER_PASSWORD`. Consultar su valor en el panel de Environment del servicio y guardarlo en un gestor de contraseñas.
5. Las variables de IA `ANTHROPIC_API_KEY` o `OPENROUTER_API_KEY` pueden configurarse como secretos en Render. No se deben publicar claves en el repositorio.
6. Abrir la URL HTTPS asignada por Render y autenticarse con usuario `opencode` y la contraseña generada.
7. Crear una sesión de prueba. Después, configurar por separado el acceso a GitHub con un token de alcance mínimo si está autorizado.

## Estado / restricciones
- Preparado en GitHub; el servicio Render todavía requiere activación desde la cuenta del titular.
- No está desplegado en Cloudflare y no modifica el proyecto BLET.
- Render ofrece la interfaz **oficial** de OpenCode. Una interfaz HTML propia sería una segunda fase.
- No cargar documentación confidencial de la empresa sin autorización.
- El motor puede ejecutar comandos: mantener autenticación activada y usar permisos limitados.
