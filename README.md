# GarrysModHelper
This repository serves as a guide for customizing your model in the game Garry's Mod. Here, you will find instructions, tips, and guides for various aspects of the game.
<details>
<summary>

# Installing Your Model on Servers
</summary>

To install your model on a server, it is necessary for the server to have the [Outfitter](https://steamcommunity.com/sharedfiles/filedetails/?id=882463775) or [PAC3](https://steamcommunity.com/sharedfiles/filedetails/?id=104691717) addon, or similar addons like Outfitter. You can easily find them by pressing the <kbd>C</kbd> key.

* To set your model in [Outfitter](https://steamcommunity.com/sharedfiles/filedetails/?id=882463775), simply choose the PlayerModel from the Steam Workshop.

* To set your model in [PAC3](https://steamcommunity.com/sharedfiles/filedetails/?id=104691717), follow these steps:
  1. To change your model in PAC3, enter the PAC3 menu via the <kbd>C</kbd> menu. Then, press the <kbd>RMB</kbd> to bring up the context menu and click on `Entity`.

      ![Image Add menu context image.](/images/pac3/context_add_menu.png)

  2. Next, add a link to the [`*.zip` archive](#creating-a-zip-file-for-pac3) containing the model files in the `model` field. To create a `*.zip` file, go to the [Creating a ZIP File for PAC3](#creating-a-zip-file-for-pac3) section.
 
      ![URL field for model in entity.](/images/pac3/url_field_for_model_in_entity.png)

  3. Then, click the `wear` button, located in the top menu under `pac` > `wear`.

      ![How to wear pac.](/images/pac3/how_to_wear.png)
</details>
<details>
<summary>

# Creating a ZIP File for PAC3
</summary>
<details>
<summary>

## Description of the ZIP File for PAC3
</summary>

In the `*.zip` file, there should be a minimum of 6 files (excluding textures):
| File Type | File Description |
| --- | --- |
| `*.dx80.vtx`   | Texture coordinate file for DirectX 8.0 |
| `*.dx90.vtx`   | Texture coordinate file for DirectX 9.0 |
| `*.mdl`        | Model file |
| `*.phy`        | Physical model file (collision) |
| `*.sw.vtx`     | Texture coordinate file for Source Engine Shader (previous versions) |
| `*.vvd`        | Vertex and animation model file |

You also need to add 2 more types of files:
| File Type | File Description |
| --- | --- |
| `*.vmt` | Texture parameter description file |
| `*.vtf` | Texture image file |

If you decompile the model, it will appear as several files: `*.smd`, `*.vta`, and `*.qc`. The materials will be located in the `*.smd` file:

![Blender materials on head](/images/model/blender_materials_on_head.png)

![Explorer vmt on head](/images/model/explorer_vmt_on_head.png)

You can move all the necessary files into the `*.zip` archive. Here are some rules for creating a correct archive:

> [!CAUTION]
> The archive must be created without compression.

> [!CAUTION]
> You should include only one `*.mdl` file and all related files.

> [!IMPORTANT]
> If the model has multiple `*.vmt` files with the same name, the model will not be displayed correctly.

> [!TIP]
> You can include all files in the archive without creating folders. This way, PAC3 will work more smoothly.
</details>
<details>
<summary>

## Creating a Correct Link
</summary>

PAC3 downloads the model and installs it on your in-game character. However, PAC3 requires a correct link that will immediately initiate the download of the `*.zip` file.

Most servers support [OneDrive](https://onedrive.live.com/), [Google Drive](https://drive.google.com/drive/), [Dropbox](https://www.dropbox.com/), and [Imgur](https://imgur.com/).

There are Garry's Mod servers where you can provide a link from any other service, such as [GitHub](https://github.com/), [Discord](https://discord.com/), and others...

> [!TIP]
> I recommend checking the [official documentation](https://wiki.pac3.info/tutorial/hosting/) for creating links.
<details>
<summary>

### OneDrive
</summary>

You need to convert the link on the [Hosting custom content online | General | PAC3 Wiki](https://wiki.pac3.info/tutorial/hosting#onedrive) website. To do this, copy the link that allows others access to your file.

![Button share in OneDrive](/images/websites/button_share_one_drive.png)

The link provided by the [website](https://wiki.pac3.info/tutorial/hosting#onedrive) can be [pasted into PAC3](#installing-your-model-on-servers).
</details>
<details>
<summary>

### Google Drive
</summary>

In Google Drive, you can right-click on the necessary file and open it for reading. The link you copy can be [pasted into PAC3](#installing-your-model-on-servers).
</details>
<details>
<summary>

### Dropbox
</summary>

To get a Dropbox link, copy the link and change the `dl=0` parameter to `dl=1`.

![Button copy link on Dropbox upload file](/images/websites/button_copy_link_on_dropbox_upload_file.png)

For example, change the link from `https://www.dropbox.com/s/8bj1qpkor7tbipu/logo.png?dl=0` to `https://www.dropbox.com/s/8bj1qpkor7tbipu/logo.png?dl=1`.
</details>
<details>
<summary>

### Imgur
</summary>

No action is needed with the Imgur link. Simply copy and paste it into the material or another field.
</details>
<details>
<summary>

### GitHub
</summary>

After uploading the file to GitHub, copy the Raw. After that, you can [paste it into PAC3](#installing-your-model-on-servers).

![Button copy raw on GitHub](/images/websites/button_copy_raw_on_github.png)
</details>
<details>
<summary>

### Discord
</summary>

To get a link to a file from Discord, right-click and copy the link.
</details>
</details>
</details>
<details>
<summary>

# Downloading Addon with Model
</summary>
<details>
<summary>

## Downloading Addon from Steam Workshop
</summary>

You can download an addon with a model from external sources or from the Steam Workshop.

There are two options to download the addon: the first one is simpler, and the second one is more reliable.
### [SteamWorkshopDownloader.io](https://steamworkshopdownloader.io/)
This is a website for downloading addons.
1. Paste the addon link into the input field.
2. If you see a download link for the addon, you can simply download it.
![steamworkshopdownloader.io example url link](/images/websites/steamworkshopdownloaderio_example_url_link.png).
3. If you don't see a download link but see the message `Question: do you know what SteamCMD is and are you logged into it?`, click on the `Yes` button and proceed to the [SteamCMD](#steamcmd) section.
![steamworkshopdownloader.io example steamcmd link](/images/websites/steamworkshopdownloaderio_example_steamcmd_link.png)
### [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD)
This is the console version of Steam.
1. Run `steamcmd.exe`.
2. Type `login anonymous` to log in to SteamCMD, or you can use `login <username> [<password>] [<Steam guard code>]` to log in to your personal account.
3. Copy the command using the `Click here to copy!` button and paste it into SteamCMD.
![steamworkshopdownloader.io example steamcmd command](/images/websites/steamworkshopdownloaderio_example_steamcmd_command.png)
4. The required addon is downloaded and located in the specified folder.
</details>
<details>
<summary>

## Extracting the Addon
</summary>

All the necessary programs can be found in the [Required Programs and Files](#required-programs-and-files) section.

| File Type | Required Program |
| --- | --- |
| `*.vpk` | [GCFScape](#2-gcfscape) |
| `*.gma` | [GWTool](#7-gwtool) |

> [!WARNING]
> GCFScape does not open files with hieroglyphs in the name.

* To extract downloaded [`*.vpk`](https://developer.valvesoftware.com/wiki/VPK) files, you can use the GCFScape application.
* To extract downloaded `*.gma` files, you can use the GWTool application. Simply run it and drag the file into the window that appears, and it will be unpacked in the same folder. (You may need the `7-Zip` archiver for additional extraction.)
</details>
</details>
<details>
<summary>

# Required Programs and Files
</summary>

## 1. Crowbar
Download link for the program [Releases · ZeqMacaw/Crowbar](https://github.com/ZeqMacaw/Crowbar/releases)<br>
This program is used for decompiling, compiling, and viewing models on Source and GoldSource with a user-friendly interface and open-source code.<br>
Valve page link: [Crowbar - Valve Developer Community](https://developer.valvesoftware.com/w/index.php?title=Crowbar)
## 2. GCFScape
Download link for the program [GCFScape](https://gamebanana.com/tools/26)<br>
GCFScape is a tool for viewing and extracting files from resource archives of Quake, GoldSrc, and Source games.<br>
Valve page link: [GCFScape - Valve Developer Community](https://developer.valvesoftware.com/wiki/GCFScape)
## 3. VTFEdit
Download link for the program [VTFLib/VTFEdit v1.3.3](https://gamebanana.com/tools/95)<br>
VTFEdit is a tool for viewing, editing, and creating VTF and VMT files.<br>
Valve page link: [VTFEdit - Valve Developer Community](https://developer.valvesoftware.com/wiki/VTFEdit)
## 4. Blender
Blender should be version `2.92` or higher. Whether it's the Steam version or from the [blender.org](https://www.blender.org/) website. Download links:
* blender.org - [Download — blender.org](https://www.blender.org/download/);
* blender.org - 2.92 - [Index of /release/Blender2.92/](https://download.blender.org/release/Blender2.92/);
* Steam - [Blender on Steam](https://store.steampowered.com/app/365670/Blender/).
## 5. default_physics.smd
File for correct rigging of the model. You can download this file from my repository by simply clicking `<> Code` -> `Download ZIP` or through this link [default_physics.smd](/files/default_physics.smd).
## 6. Blender Source Tools
Download link for Blender add-on [Blender Source Tools](http://steamreview.org/BlenderSourceTools/download)  
Blender Source Tools add support for the _Source Engine_ to _Blender_, a free 3D modeling package. Whether you're making a simple hat or a fully articulated character, Blender Source Tools make exporting easier.  
Valve page link: [Blender Source Tools - Valve Developer Community](https://developer.valvesoftware.com/wiki/Blender_Source_Tools)
## 7. GWTool
Download link [GWTool](https://github.com/fgblomqvist/gwtool/releases).  
This application is needed to unpack `*.gma` files.
## 8. ProportionTrick Script
Download link [ProportionTrick Script](https://github.com/sksh70/proportion_trick_script).<br>
This is a special script for creating model proportions.
## 9. 7-Zip
Download link [7-Zip](https://www.7-zip.org/).<br>
This application is needed for working with archives.
</details>
<details>
<summary>

# Setting Up Programs
</summary>

## 1. Crowbar
You need to specify the path to `steam.exe`. To do this, open the `Set Up Games` tab and click the `Browse...` button next to the text `Steam executable (steam.exe) [Used for "Run Game" button]:`.  
If you need to specify the path to the game, you can do it in the same tab by selecting the game in the upper ComboBox.

## 2. Blender
You need to add `Blender Source Tools` as an add-on in Blender. Step-by-step instructions:
1. Click the `Edit` button (next to the application header).
2. Click the `Preferences` button.
3. Click the `Add-ons` button (left side in the opened window).
4. Click the `Install` button.
5. Choose the path to `blender_source_tools_3.2.5.zip`.
6. Check the box for `Import-Export: Blender Source Tools`.
Now you can import and export models in the `*.smd` and `*.dmx` formats.
</details>

<details>
<summary>

# License
</summary>

GarrysModHelper © 2024 is licensed under Attribution-NonCommercial-NoDerivatives 4.0 International. To view a copy of this license, visit [http://creativecommons.org/licenses/by-nc-nd/4.0/](http://creativecommons.org/licenses/by-nc-nd/4.0/).
</details>

<details>
<summary>

# Other languages
</summary>

* [English version](/README.md)
* [Русская версия](/README_ru.md)
</details>