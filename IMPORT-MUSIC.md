## 🎶 Cómo importar una canción personalizada

Para agregar tu propia música al **Music Player para Minecraft Bedrock Edition**, sigue estos pasos:

1. **Formato del archivo**: Asegúrate de que tu archivo de música esté en formato **.mp3**.

2. **Conversión a .ogg**: Convierte el archivo **.mp3** a **.ogg** para que el juego lo detecte. Puedes usar herramientas en línea o software como Audacity para hacer esta conversión.

3. **Mover el archivo**: Una vez convertido, mueve el archivo **.ogg** a la carpeta `Music Ui/sounds/music/`, y asígnale un nombre. Por ejemplo, puedes llamarlo `music_0.ogg`.

4. **Configuración en JSON**:
   - Abre el archivo `Music Ui/ui/music/music_screen.json`. En este archivo, hay una sección llamada **'music_custom_user'**.
   - Dentro de esta sección, encontrarás una serie de variables predefinidas con comentarios (//). Deberás eliminar estos comentarios (//) para habilitar la configuración.

5. **Edición de variables**:
   - **$music_name**: Aquí ingresa el nombre de la canción.
   - **$music_time**: Establece la duración de la canción (en minutos y segundos).
   - **$music_creator**: Indica el nombre del creador de la música.
   - **$music_button_sound_name**: Esta variable debe coincidir con el nombre que asignarás en el archivo `sound_definitions.json` (lo explicaremos en el siguiente paso).

6. **Editar `sound_definitions.json`**:
   - Abre el archivo `sound_definitions.json` con un editor de texto.
   - Escribe la siguiente estructura de código:

     ```json
     "music.music_custom_variable": {
       "category": "ui",
       "sounds": [
         {
           "name": "sounds/music/funk_estranho",
           "stream": true,
           "volume": 1.0,
           "load_on_low_memory": true
         }
       ]
     }
     ```

   - La variable que colocaste anteriormente en **$music_button_sound_name** (por ejemplo, `music.music_custom_variable`) debe coincidir con la que aparece en el código de ejemplo, en **"music.music_custom_variable"**.
   
   - En el elemento `"name"`, debes escribir la ruta del archivo de música que moviste previamente. Siguiendo el ejemplo, si tu canción es **my_music_custom.ogg** y la colocaste en la carpeta `sounds/music/`, la ruta será:

     ```json
     "name": "sounds/music/my_music_custom"
     ```

---

Con estos pasos, podrás añadir y configurar canciones personalizadas en el reproductor de música para Minecraft Bedrock.
