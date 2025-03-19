# 💻 **How to Import a Custom Song on Desktop**

Follow these steps to add your own music to **Music Ore-UI**:

### 1. **Convert Your Music File**

-   Make sure your music is in `.mp3` format.
-   Convert it to `.ogg` using tools like [Audacity](https://www.audacityteam.org/) or online converters like [Online Audio Converter](https://online-audio-converter.com/).
    -   **Note**: The `.ogg` format is preferred for Minecraft Bedrock, as it is more efficient and compatible.

### 2. **Place the File in the Correct Folder**

-   Move the `.ogg` file to the `Music Ore-UI/sounds/music/` folder.
-   Name the file descriptively, for example: `my_song.ogg`.
    -   **Tip**: Use simple names without spaces or special characters to avoid compatibility issues.

### 3. **Update the Configuration**

1. Open the **Music Ore-UI** pack folder.
2. Locate the **`music_list.json`** file and edit it to add your song. You need to modify the following variables:

    - **`$songName`**: The name of the song (it will appear in the player interface).
    - **`$songDuration`**: The duration of the song in `MM:SS` format.
    - **`$songAuthor`**: The name of the artist or author of the song.
    - **`$songCover`**: (Optional) The path to the song's cover image.
    - **`$songAudio`**: This must match the key defined in `sound_definitions.json`.

    **Example**:

    ```json
   {
        "my_custom_song@music.list_item_grid": {
            "$songAudio": "music.my_song",
            "$songName": "Song Name",
            "$songAuthor": "Artist Name",
            "$songDuration": "03:45",
            "$songCover": "textures/covers/my_cover" // Optional
        }
    }
    ```

### 4. **Define the Sound in `sound_definitions.json`**

1. Open the `sound_definitions.json` file and add a new entry for your song:

    ```json
    "music.my_song": {
       "category": "ui",
       "sounds": [
          {
             "name": "sounds/music/my_song",
             "stream": true,
             "volume": 1.0,
             "load_on_low_memory": true
          }
       ]
    }
    ```

2. Make sure the `"name"` value points to your `.ogg` file without the extension.

### 5. **Add a Cover (Optional)**

-   If you want to add a cover image for the song:
    1. Place the image in the `textures/covers/` folder.
    2. Name the image descriptively, for example: `my_cover.png`.
    3. Specify the image path in the **`$songCover`** variable within `music_list.json`.

### 6. **Verify and Test**

-   Ensure that all file names and paths are consistent in `music_list.json` and `sound_definitions.json`.
-   Import the pack into Minecraft Bedrock and activate the music player to test your custom song.

---

### 🛠️ **Tips and Troubleshooting**

-   **Music doesn't play**:

    -   Verify that the music file is in `.ogg` format.
    -   Make sure the file name in `sound_definitions.json` exactly matches the file name in the `sounds/music/` folder.

-   **The player doesn't show the song**:

    -   Check that the entries in `music_list.json` are correctly written and that there are no syntax errors (such as missing commas or misplaced brackets).
    -   Ensure that the **`$songAudio`** value matches the key defined in `sound_definitions.json`.

-   **Issues with the cover**:
    -   If the cover image doesn't appear, verify that the path in **`$songCover`** is correct and that the image is in the `textures/covers/` folder.

---

# 📱 **How to Import Custom Music from a Mobile Device**

If someone wants to follow the steps to import custom music into **Music Ore-UI** from a mobile device, the process can be a bit more complicated than on a computer, but it's not impossible. Here's how they can do it and what tools they'll need:

---

#### 1. **Convert the Music File**
   - **Required Tools**: An audio conversion app, such as [Media Converter](https://play.google.com/store/apps/details?id=com.mediamanager) (available on Google Play) or [Audio Converter](https://apps.apple.com/us/app/audio-converter-audio-convert/id1182165164) (available on the App Store).
   - **Steps**:
     1. Download the audio conversion app.
     2. Convert your music file to `.ogg` format. Make sure to select the `.ogg` option in the output settings.

#### 2. **Move the File to the Correct Folder**
   - **Required Tools**: A file manager app, such as [Files by Google](https://play.google.com/store/apps/details?id=com.google.android.apps.nbu.files) (Android) or [File Explorer](https://apps.apple.com/us/app/file-explorer-file-manager/id1232058109) (iOS).
   - **Steps**:
     1. Download the **Music Ore-UI** pack to your device.
     2. Use the file manager to unzip the `.mcpack` file (if necessary).
     3. Navigate to the `Music Ore-UI/sounds/music/` folder and move your converted `.ogg` file there.
     4. Rename the file descriptively, for example: `my_song.ogg`.

#### 3. **Edit `music_list.json` and `sound_definitions.json`**
   - **Required Tools**: A text editor for mobile, such as [QuickEdit](https://play.google.com/store/apps/details?id=com.rhmsoft.edit) (Android) or [Textastic](https://apps.apple.com/us/app/textastic-code-editor-9/id1049254261) (iOS).
   - **Steps**:
     1. Open the `music_list.json` file with the text editor.
     2. Add a new entry for your song, following the format provided in the guide.
     3. Open the `sound_definitions.json` file and add the sound definition for your song.
     4. Save the changes.

#### 4. **Add a Cover (Optional)**
   - **Required Tools**: An image editor (optional) and the file manager.
   - **Steps**:
     1. If you want to add a cover, place the image in the `textures/covers/` folder.
     2. Make sure the image path is correctly specified in `music_list.json`.

#### 5. **Import the Pack into Minecraft**
   - **Steps**:
     1. Compress the pack folder into a `.zip` file (you can use apps like [RAR](https://play.google.com/store/apps/details?id=com.rarlab.rar) for Android or [iZip](https://apps.apple.com/us/app/izip-zip-unzip-unrar-tool/id413971331) for iOS).
     2. Change the file extension from `.zip` to `.mcpack`.
     3. Open Minecraft Bedrock and go to **Settings > Resource Packs**.
     4. Import the `.mcpack` file and activate it in the world where you want to use the music player.

---

### 🛠️ **Common Mobile Challenges**

1. **Editing JSON Files**:
   - Editing JSON files on a mobile device can be tedious due to the small screen and lack of a physical keyboard. I recommend using a text editor with syntax highlighting to avoid errors.

2. **File Conversion**:
   - Some audio conversion apps may have limitations on output quality or the number of files that can be converted for free. Make sure to use a reliable app.

3. **File Management**:
   - On iOS devices, access to certain folders may be restricted. Use apps like **File Explorer** to access the necessary folders.

4. **Compatibility**:
   - Make sure the `.ogg` file is properly converted and doesn't have encoding issues that could prevent it from playing in Minecraft.

---

### 💡 **Tips to Make It Easier**

- **Use a Computer if Possible**: While it's possible to do this on a mobile device, the process will be faster and less error-prone if done on a computer.
- **Follow the Guide Step by Step**: Carefully read each step and verify that file names and paths are correct.

---

### 💬 **Additional Support**

If you're still having issues or need further assistance, feel free to join our [Discord Server](https://discord.gg/kYDf4gadKw). We're here to help!
