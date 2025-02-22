## 🎶 How to Import a Custom Song

Follow these steps to add your own music to **Music Ui**:

### 1. Convert Your Music File

-   Ensure your music is in `.mp3` format.
-   Convert it to `.ogg` using tools like [Audacity](https://www.audacityteam.org/) or online converters.

### 2. Place the File

-   Move the `.ogg` file to the `Music Ui/sounds/music/` folder.
-   Name it appropriately, e.g., `music_1.ogg`.

### 3. Update the Configuration

1. Open `Music Ui` folder.
2. Locate **"music_list.json"** and edit the variables:

    - **`$songName`**: Song name.
    - **`$SongDuration`**: Duration (MM:SS).
    - **`$songAuthor`**: Artist name.
    - **`$songCover`**: Cover image path (optional).
    - **`$songAudio`**: Match this with the key in `sound_definitions.json`.

    Example:

    ```json
    "my_custom_music@music.list_item_grid": {
       "$songAudio": "music.music_1",
       "$songName": "Music Name",
       "$songAuthor": "Artist Name",
       "$songDuration": "02:30",
       "$songCover": "textures/covers/cover_1" // Optional
    }
    ```

### 4. Define the Sound

1. Open `sound_definitions.json` and add:

    ```json
    "music.music_1": {
       "category": "ui",
       "sounds": [
          {
             "name": "sounds/music/my_music.ogg",
             "stream": true,
             "volume": 1.0,
             "load_on_low_memory": true
          }
       ]
    }
    ```

2. Ensure `"name"` points to your `.ogg` file without the extension.

### Notes

-   To add a thumbnail, specify its path in **`$songCover`**.
-   Verify all paths and names are consistent across files.

---

By following these steps, you’ll be able to add and configure custom songs in the music player for Minecraft Bedrock.
