## 🎶 How to Import a Custom Song

To add your own music to the **Music Ui**, follow these steps:

1. **File Format**: Make sure your music file is in `.mp3` format.

2. **Convert to .ogg**: Convert the `.mp3` file to `.ogg` so that the game can detect it. You can use online tools or software like Audacity for this conversion.

3. **Move the File**: Once converted, move the `.ogg` file to the `Music Ui/sounds/music/` folder and give it a name. For example, you can name it `music_custom.ogg`.

4. **Configuration in JSON**:
   - Open the file `Music Ui/ui/music/music_screen.json`. In this file, there is a section called **'music_custom_user'**.
   - Inside this section, you will find a series of predefined variables with comments (//). You need to remove these comments (//) to enable the configuration:

      ```json
      "$music_name": ""
      "$music_time": "",
      "$music_creator": "",
      "$music_button_sound_name": ""
      ```

5. **Editing Variables**:
   - **$music_name**: Enter the name of the song here.
   - **$music_time**: Set the duration of the song (in minutes and seconds).
   - **$music_creator**: Specify the name of the music creator.
   - **$music_button_sound_name**: This variable must match the name you will assign in the `sound_definitions.json` file (we'll explain this in the next step).

6. **Editing `sound_definitions.json`**:
   - Open the `sound_definitions.json` file with a text editor.
   - Write the following code structure:

     ```json
     "music.music_custom_variable": {
       "category": "ui",
       "sounds": [
         {
           "name": "sounds/music/music_custom_path",
           "stream": true,
           "volume": 1.0,
           "load_on_low_memory": true
         }
       ]
     }
     ```

   - The variable you used in **$music_button_sound_name** (for example, `music.music_custom_variable`) must match the one that appears in this code example, in **"music.music_custom_variable"**.
   
   - In the `"name"` field, you must write the path to the music file you moved earlier. Following the example, if your song is **my_music_custom.ogg** and you placed it in the `sounds/music/` folder, the path will be:

     ```json
     "name": "sounds/music/my_music_custom"
     ```

---

By following these steps, you will be able to add and configure custom songs in the music player for Minecraft Bedrock.
