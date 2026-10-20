## 🎶 How to Import a Custom Song

Follow these steps to add your own music to **Music UI**:

### 1. Convert Your Music File

- Ensure your music is in `.mp3` or `.wav` format.
- Convert it to `.ogg` using tools like [Convertio](https://convertio.co/mp3-ogg/) or any online converter.

### 2. Place the File in the Correct Folder

- Move your `.ogg` file to `Music UI/sounds/music/...` inside your resource pack.
- Name it descriptively, for example: `my_song.ogg`.

### 3. Update the Song List

1. Open `Music UI/ui/music_list.json`.
2. Locate the **"custom_list_content"** block.
3. Add a new entry using the `music.music_track_card` template:

    ```json
    "my_track@music.music_track_card": {
      "$songCover": "textures/covers/my_cover",       // Cover path (optional)
      "$songName": "My Favorite Song",               // Song name
      "$songDuration": "03:45",                      // Duration in MM:SS
      "$songArtist": "Unknown Artist",               // Artist name
      "$songAudio": "music.my_song",                 // Key in sound_definitions.json
      "$songPath": "sounds/music/my_song"            // Path inside sounds folder
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
2. `name`: points to your `.ogg` file without the extension.
3. `stream`: Keep `true` to play long files without loading them fully into memory.

### Notes

- To add a thumbnail, specify its path in **`$songCover`**.
- Verify all paths and names are consistent across files.

---

By following these steps, you’ll be able to add and configure custom songs in the music player for Minecraft Bedrock.
