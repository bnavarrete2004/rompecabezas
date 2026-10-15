# Instrucciones para agentes

Estas instrucciones se aplican a todo el proyecto. Lee también `PROJECT_STATE.md` antes de proponer o realizar cambios.

## Objetivo

Crear un juego web privado de rompecabezas cooperativo para dos personas. Las partidas se compartirán mediante un enlace de sala y se accederá al servidor local a través de ngrok. La experiencia debe ser sencilla y recordar a los juegos Flash de la década de 2010.

## Reglas de trabajo

1. **Pruebas unitarias para todos los cambios.** Cada cambio de código debe quedar cubierto por pruebas unitarias pertinentes, tanto si añade comportamiento como si corrige o modifica el existente. Si hace falta una prueba nueva, el agente puede crearla sin pedir permiso adicional. Los cambios de documentación deben validarse con las comprobaciones automatizadas pertinentes.
2. **Verificación antes de entregar o registrar cambios.** Ejecuta las pruebas aplicables al cambio y comprueba que todas pasen antes de darlo por terminado, guardarlo como versión o crear un commit. Si alguna falla, corrige el problema y vuelve a ejecutarlas. No declares un cambio como verificado si no se han podido ejecutar.
3. **Alcance de las pruebas.** Si el cambio afecta solo una sección o módulo, ejecuta sus pruebas unitarias y las pruebas de regresión necesarias para comprobar que no introduce errores. Si afecta varias secciones, contratos compartidos, configuración o integración, ejecuta la batería completa. Documenta qué se ejecutó y el resultado.
4. **Diseño sujeto a elección del usuario.** Antes de cambiar el diseño visual, la apariencia o la interacción de la interfaz, presenta **tres prototipos distintos** con sus diferencias concretas y espera a que el usuario elija uno. No implementes ese cambio de diseño antes de recibir su elección. Esta regla también aplica al primer diseño del juego.
5. **Mantén el estado actualizado.** Actualiza `PROJECT_STATE.md` cuando cambien decisiones, alcance, avances, bloqueos o próximos pasos. Distingue hechos confirmados, propuestas y asuntos pendientes.

## Criterios técnicos acordados hasta ahora

- Se recomendó TypeScript con Phaser para el juego, Node.js con Socket.IO para sincronizar las salas y Vite para el cliente. Es una recomendación, no una elección definitiva del usuario.
- La primera versión puede guardar el estado de las partidas en memoria; esto implica que se pierde al reiniciar el servidor.
- Se propusieron dificultades iniciales de 9, 16 y 36 piezas y encaje automático al acercar una pieza a su sitio. Estos detalles aún pueden ajustarse con el usuario.
- Se recomendó permitir que quien crea la sala suba una imagen propia. No incorpores imágenes encontradas en internet al repositorio sin comprobar sus condiciones de uso.
- El enlace de ngrok expone el servidor a internet. La sala necesita un identificador difícil de adivinar y un límite de dos participantes.

## Estado actual

El proyecto está en planificación. No hay aplicación ni pruebas implementadas. No escribas código de la aplicación hasta que el usuario lo solicite; antes de implementar su diseño, cumple la regla de los tres prototipos.
