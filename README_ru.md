# GarrysModHelper
Этот репозиторий представляет собой мануал для кастомизации своей модельки в игре Garry's Mod. Здесь вы найдёте инструкции, советы и руководства для различных аспектов игры.
<details>
<summary>

# Установка Своей Модели на Серверах
</summary>

Чтобы установить свою модельку на сервере необходимо, чтобы на сервере был установлен аддон [Outfitter](https://steamcommunity.com/sharedfiles/filedetails/?id=882463775) или [PAC3](https://steamcommunity.com/sharedfiles/filedetails/?id=104691717), либо аддоны, подобные Outfitter. Их можно найти сразу, если зажать кнопку <kbd>C</kbd>.

* Чтобы поставить модельку в [Outfitter](https://steamcommunity.com/sharedfiles/filedetails/?id=882463775) достаточно выбрать PlayerModel в мастерской Steam

* Чтобы поставить модельку в [PAC3](https://steamcommunity.com/sharedfiles/filedetails/?id=104691717) необходимо сделать следующее:
  1. Чтобы изменить свою модельку в PAC3 необходимо зайти в меню PAC3 через <kbd>C</kbd>-меню. Далее необходимо нажать <kbd>ПКМ</kbd>, чтобы вызвать контекстное меню и нажать на `Entity`.

      ![Image Add menu context image.](/images/pac3/context_add_menu.png)

  2. После этого необходимо добавить ссылку на [`*.zip` архив](#создание-zip-файла-для-pac3) с моделькой в поле `model`. Который содержит файлы с моделькой. Чтобы создать `*.zip` файл необходимо перейти к пункту [Создание ZIP файла для PAC3](#создание-zip-файла-для-pac3).
 
      ![URL field for model in entity.](/images/pac3/url_field_for_model_in_entity.png)

  3. Дальше необходимо нажать на кнопку `wear`. Она находится в верхней менюшке `pac` > `wear`.

      ![How to wear pac.](/images/pac3/how_to_wear.png)
</details>
<details>
<summary>

# Создание ZIP Файла для PAC3
</summary>
<details>
<summary>

## Описание ZIP Файла для PAC3
</summary>

В `*.zip` файле должно быть минимум 6 файлов (не включая текстуры):
| Тип файла | Описание файла |
| --- | ---  |
| `*.dx80.vtx`   | Файл текстурных координат для DirectX 8.0 |
| `*.dx90.vtx`   | Файл текстурных координат для DirectX 9.0 |
| `*.mdl`        | Файл модели |
| `*.phy`        | Файл физической модели (коллизии) |
| `*.sw.vtx`     | Файл текстурных координат для Source Engine Shader (прошлые версии) |
| `*.vvd`        | Файл вершин и анимаций модели |

Также необходимо добавить ещё 2 типа файлов:
| Тип файла | Описание файла |
| --- | --- |
| `*.vmt` | Файл описания параметров текстуры |
| `*.vtf` | Файл с изображением текстуры |

Если декомпилировать модель, то она будет выглядеть в виде нескольких файлов: `*.smd`, `*.vta` и `*.qc`. Именно в `*.smd` файле и будут находится материалы:

![Blender materials on head](/images/model/blender_materials_on_head.png)

![Explorer vmt on head](/images/model/explorer_vmt_on_head.png)

Вы можете перекинуть все необходимые файлы в `*.zip` архив. Вот несколько правил для создания корректного архива:

> [!CAUTION]
> Создавать архив необходимо без сжатия.

> [!CAUTION]
> Вы должны скинуть только один `*.mdl` файл и все относящиеся к нему файлы.

> [!IMPORTANT]
> Если у модели есть несколько `*.vmt` файлов с одинаковым названием, то модель не будет корректно отображаться.

> [!TIP]
> Вы можете скинуть все файлы в архив, не создавая папок. Так PAC3 будет работать корректнее.
</details>
<details>
<summary>

## Создание Корректной Ссылки
</summary>

PAC3 скачивает модель и устанавливает её на вашего игрового персонажа. Однако PAC3 необходимо корректная ссылка, которая будет сразу открывать загрузку `*.zip` файла.

Большинство серверов поддерживают [OneDrive](https://onedrive.live.com/), [Google Drive](https://drive.google.com/drive/), [Dropbox](https://www.dropbox.com/) и [Imgur](https://imgur.com/).

Есть сервера Garry's Mod, на которых можно поставить ссылку на любой другой сервис, например [GitHub](https://github.com/), [Discord](https://discord.com/) и прочие...

> [!TIP]
> Советую ознакомиться с [официальной документацией](https://wiki.pac3.info/tutorial/hosting/) на создание ссылок.
<details>
<summary>

### OneDrive
</summary>

Вам необходимо конвертировать ссылку на сайте [Hosting custom content online | General | PAC3 Wiki](https://wiki.pac3.info/tutorial/hosting#onedrive). Для этого необходимо скопировать ссылку, которая даёт другим пользователям доступ к вашему файлу.

![Button share in OneDrive](/images/websites/button_share_one_drive.png)

Ссылку которую выдаст [сайт](https://wiki.pac3.info/tutorial/hosting#onedrive) можно будет [вставить в PAC3](#установка-своей-модели-на-серверах).
</details>
<details>
<summary>

### Google Drive
</summary>

В Google Drive вы можете нажать <kbd>ПКМ</kbd> на необходимый файл и открый доступ для чтения. Ссылку, которую вы скопируете можно будет [вставить в PAC3](#установка-своей-модели-на-серверах).
</details>
<details>
<summary>

### Dropbox
</summary>

Чтобы получить ссылку Dropbox необходимо скопировать ссылку и изменить параметр `dl=0` на `dl=1`.

![Button copy link on Dropbox upload file](/images/websites/button_copy_link_on_dropbox_upload_file.png)

Например ссылку `https://www.dropbox.com/s/8bj1qpkor7tbipu/logo.png?dl=0` нужно изменить на `https://www.dropbox.com/s/8bj1qpkor7tbipu/logo.png?dl=1`.
</details>
<details>
<summary>

### Imgur
</summary>

С ссылкой от Imgur ничего делать не нужно. Достаточно лишь скопировать и вставить её в поле материала или чего-то ещё.
</details>
<details>
<summary>

### GitHub
</summary>

После загрузки файла на GitHub необходимо скопировать Raw. После этого можно будет [вставить в PAC3](#установка-своей-модели-на-серверах).

![Button copy raw on GitHub](/images/websites/button_copy_raw_on_github.png)
</details>
<details>
<summary>

### Discord
</summary>

Чтобы получить ссылку на файл из Discord нужно нажать <kbd>ПКМ</kbd> и скопировать ссылку.
</details>
</details>
</details>
<details>
<summary>

# Лицензия
</summary>

GarrysModHelper © 2024 имеет лицензию Attribution-NonCommercial-NoDerivatives 4.0 International. Чтобы просмотреть копию этой лицензии, посетите [http://creativecommons.org/licenses/by-nc-nd/4.0/](http://creativecommons.org/licenses/by-nc-nd/4.0/).
</details>

<details>
<summary>

# Другие языки
</summary>

* [English version](/README.md)
* [Русская версия](/README_ru.md)
</details>