# Estado del proyecto

**Fecha de actualización:** 2026-10-14  
**Fase:** planificación  
**Implementación:** no iniciada

## Idea y objetivo

Juego web privado para que dos personas armen un rompecabezas juntas en tiempo real. Se ejecutará localmente y se compartirá mediante ngrok. Las temáticas de interés iniciales son Gintama y Chiikawa, con diferentes dificultades definidas por la cantidad de piezas. La apariencia y el comportamiento deseados recuerdan a los juegos Flash sencillos de la década de 2010.

## Decisiones confirmadas por el usuario

- El juego debe permitir una partida cooperativa en línea para dos personas.
- Se desea usar ngrok para compartir el servidor local.
- Habrá distintas temáticas y dificultades basadas en el número de piezas.
- Se consideran imágenes obtenidas de internet para crear rompecabezas; la fuente y los permisos concretos todavía no están definidos.
- Antes de cualquier cambio de diseño, el agente debe presentar tres prototipos y esperar la elección del usuario.
- Todos los cambios requieren pruebas unitarias pertinentes; antes de dar por terminados o registrar los cambios, las pruebas aplicables deben pasar. Para cambios limitados a una sección, se ejecutan las pruebas de esa sección y las regresiones necesarias.

## Propuesta técnica pendiente de aprobación

| Parte | Recomendación | Motivo |
| --- | --- | --- |
| Cliente | TypeScript, Phaser y Vite | Phaser proporciona un lienzo de juego, arrastre de piezas y entrada con mouse o tacto; Vite facilita el desarrollo. |
| Servidor | Node.js y Socket.IO | Salas, comunicación en tiempo real y reconexión. |
| Estado inicial | En memoria en el servidor | Suficiente para una primera versión de dos personas; se pierde al reiniciar. |
| Acceso | Un único servidor local expuesto con ngrok | El cliente y la conexión de juego pueden usar el mismo origen. |

## Alcance sugerido para una primera versión

1. Crear una sala e invitar a otra persona mediante un enlace.
2. Elegir una imagen y una dificultad de 9, 16 o 36 piezas.
3. Mover piezas en un tablero compartido; sincronizar posiciones y piezas encajadas.
4. Mostrar el progreso y una referencia de la imagen completa.
5. Limitar la sala a dos participantes y admitir reconexión mientras el servidor siga activo.

Este alcance es una propuesta; aún no se ha autorizado la implementación.

## Imágenes

Se recomendó que quien crea la sala pueda subir una imagen desde su dispositivo, en vez de depender de una URL externa. Algunas imágenes remotas impiden el procesamiento necesario para recortar piezas en el navegador. Antes de incluir una galería fija de Gintama, Chiikawa u otras obras, habrá que comprobar las condiciones de uso de cada imagen. Una imagen visible en internet no implica permiso para incorporarla al juego.

## Pendiente de decidir

- Confirmar o cambiar la propuesta de tecnologías.
- Elegir cómo se aportarán las imágenes: subida local, galería con permisos verificados o ambas.
- Definir si la primera versión será solo para escritorio o también para móvil.
- Cuando se vaya a diseñar la interfaz, presentar tres prototipos y esperar la elección del usuario.
- Definir si se necesita conservar partidas después de reiniciar el servidor.

## Estado de los archivos

Por ahora solo existen estos documentos de planificación. No hay código de aplicación, dependencias ni batería de pruebas.
