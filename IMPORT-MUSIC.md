## 🎶 How to Import a Custom Song

Follow these steps to add your own music to **Music Ui**:

### 1. Convert Your Music File
- Ensure your music is in `.mp3` format.
- Convert it to `.ogg` using tools like [Audacity](https://www.audacityteam.org/) or online converters.

### 2. Place the File
- Move the `.ogg` file to the `Music Ui/sounds/music/` folder.
- Name it appropriately, e.g., `my_music.ogg`.

### 3. Update the Configuration
1. Open `Music Ui/ui/music/music_screen.json`.
2. Locate **"music_custom_user"** and edit the variables:
   - **`$music_name`**: Song name.
   - **`$music_time`**: Duration (MM:SS).
   - **`$music_creator`**: Artist name.
   - **`$music_button_sound_name`**: Match this with the key in `sound_definitions.json`.

   Example:
   ```json
   "custom_music_example@music_common.music_header_section": {
      "$show_blank_label": false,
      "$music_icon_texture": "textures/music/my_thumbnail",
      "$music_name": "Custom Song",
      "$music_time": "03:45",
      "$music_creator": "Unknown Artist",
      "$music_button_sound_name": "music.custom_music"
   }
   ```

### 4. Define the Sound
1. Open `sound_definitions.json` and add:
   ```json
   "music.custom_music": {
      "category": "ui",
      "sounds": [
         {
            "name": "sounds/music/my_music",
            "stream": true,
            "volume": 1.0,
            "load_on_low_memory": true
         }
      ]
   }
   ```
2. Ensure `"name"` points to your `.ogg` file without the extension.

### Notes
- To add a thumbnail, specify its path in **`$music_icon_texture`**.
- Verify all paths and names are consistent across files.

---

By following these steps, you’ll be able to add and configure custom songs in the music player for Minecraft Bedrock.
