## 🎶 How to Import a Custom Song

To add your own music to **Music Ui**, follow these steps:

1. **File Format**: Ensure your music file is in `.mp3` format.

2. **Convert to .ogg**: Convert the `.mp3` file to `.ogg` so that the game can detect it. You can use online tools or software like Audacity for this conversion.

3. **Move the File**: After conversion, move the `.ogg` file to the `Music Ui/sounds/music/` folder and give it a name, for example, `music_custom.ogg`.

4. **Configuration in JSON**:
   - Open the file `Music Ui/ui/music/music_screen.json`. In this file, locate the section **"music_custom_user"**.
   - Inside this section, you’ll find a set of predefined variables with comments (//). Remove the comments (//) to enable the configuration:

      ```json
      "$music_name": "",
      "$music_time": "",
      "$music_creator": "",
      "$music_button_sound_name": ""
      ```

5. **Editing Variables**:
   - **$music_name**: Enter the song name.
   - **$music_time**: Set the song duration (in minutes and seconds).
   - **$music_creator**: Specify the name of the music creator.
   - **$music_button_sound_name**: This should match the name defined in `sound_definitions.json` (explained in Step 6).
   - **$show_blank_label**: If set to `true`, only the text will appear if the image is missing. If set to `false`, you’ll need to specify an image for the thumbnail with `"$music_icon_texture"`.
   - **Example Code**:

     ```json
     "custom_music_example@music_common.music_header_section": {
        "$show_blank_label": false, // Show music thumbnail
        "$music_icon_texture": "textures/music/music_thumbnail_image", // Image Path
        "$music_name": "My Song",
        "$music_time": "02:00",
        "$music_creator": "All Music",
        "$music_button_sound_name": "music.music_0"
     }
     ```

6. **Editing `sound_definitions.json`**:
   - Open `sound_definitions.json` in a text editor.
   - Add the following structure:

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

   - Ensure that the variable you used in **$music_button_sound_name** (e.g., `music.music_custom_variable`) matches the one in this example, `"music.music_custom_variable"`.
   
   - In the `"name"` field, specify the path to your custom music file. For instance, if your song is named `my_music_custom.ogg` and is in the `sounds/music/` folder, the path will be:

     ```json
     "name": "sounds/music/my_music_custom" // Music Path
     ```

By following these steps, you’ll be able to add and configure custom songs in the music player for Minecraft Bedrock.
