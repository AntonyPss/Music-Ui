## 🎶 Cómo importar una canción personalizada

Para agregar tu propia música al **Music Player para Minecraft Bedrock Edition**, sigue estos sencillos pasos:

1. **Formato del archivo**: Asegúrate de que tu archivo de música esté en formato **.mp3**.
   
2. **Conversión a .ogg**: Convierte el archivo **.mp3** a **.ogg** para que el juego lo pueda detectar. Puedes usar herramientas en línea o software como Audacity para hacer esta conversión.

3. **Mover el archivo**: Una vez convertido, mueve el archivo **.ogg** a la carpeta `Music Ui/sounds/music/`, y asígnale un nombre. Por ejemplo, puedes llamarlo `music_0.ogg`.

4. **Configuración en JSON**:
   - Abre el archivo `Music Ui/ui/music/music_screen.json`. En este archivo, hay una sección llamada **'music_custom_user'**.
   - Dentro de esta sección, encontrarás una serie de variables predefinidas con comentarios (//). Deberás eliminar estos comentarios (//) para habilitar la configuración.

5. **Edición de variables**:
   - **$music_name**: Aquí ingresa el nombre de la canción.
   - **$music_time**: Establece la duración de la canción (en minutos y segundos).
   - **$music_creator**: Indica el nombre del creador de la música.
   - **$music_button_sound_name**: Esta variable debe coincidir con una definición en el archivo `sound_definitions.json`. Aquí defines cómo se llamará el sonido en el juego.

Una vez completados estos pasos, tu canción personalizada debería aparecer en el reproductor de música dentro del juego y estar lista para reproducirse.
