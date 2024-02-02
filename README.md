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