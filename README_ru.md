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
> 
> Создавать архив необходимо без сжатия.

> [!CAUTION]
> 
> Вы должны скинуть только один `*.mdl` файл и все относящиеся к нему файлы.

> [!CAUTION]
> 
> Если у вас не 6 файлов модельки, то скорее всего вам придётся перекомпилировать модель. Это можно сделать в пункте [компиляция `*.mdl` и её особенности](#компиляция-mdl-и-её-особенности)

> [!IMPORTANT]
> 
> Если у модели есть несколько `*.vmt` файлов с одинаковым названием, то модель не будет корректно отображаться.

> [!TIP]
> 
> Вы можете скинуть все файлы в архив, не создавая папок. Так PAC3 будет работать корректнее.
</details>
<details>
<summary>

## Создание Корректной Ссылки
</summary>

PAC3 скачивает модель и устанавливает её на вашего игрового персонажа. Однако PAC3 необходимо корректная ссылка, которая будет сразу открывать загрузку `*.zip` файла.

Большинство серверов поддерживают [OneDrive](https://onedrive.live.com/), [Google Drive](https://drive.google.com/drive/), [Dropbox](https://www.dropbox.com/) и [Imgur](https://imgur.com/).

Есть сервера Garry's Mod, на которых можно поставить ссылку на любой другой сервис, например [GitHub](https://github.com/), [Discord](https://discord.com/) и прочие...

> [!TIP] Совет
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

# Скачать аддон с моделькой
</summary>
<details>
<summary>

## Скачка аддона из Steam Workshop
</summary>

Вы можете скачать аддон с моделькой из сторонних источников, либо из Steam Workshop. 

Есть два варианта, чтобы скачать аддон первый проще, а второй надёжнее.
### [SteamWorkshopDownloader.io](https://steamworkshopdownloader.io/)
Это сайт для скачки аддонов.
1. Вставьте ссылку на аддон в поле ввода.
2. Если у вас появилась ссылка для скачки аддона, то можно просто скачать и на этом всё.
![steamworkshopdownloader.io example url link](/images/websites/steamworkshopdownloaderio_example_url_link.png).
3. Если у вас не появилась ссылка на скачку и появилась надпись `Question: do you know what SteamCMD is and are you logged into it?`, то нажмите на кнопку `Yes` и переходите на пункт [SteamCMD](#steamcmd).
![steamworkshopdownloader.io example steamcmd link](/images/websites/steamworkshopdownloaderio_example_steamcmd_link.png)
### [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD)
Это консольная версия Steam.
1. Запускаете `steamcmd.exe`.
2. Вписывайте `login anonymous`, чтобы войти в SteamCMD, либо можно написать `login <username> [<password>] [<Steam guard code>]`, чтобы войти в свой личный аккаунт.
3. Скопируйте команду через кнопку `Click here to copy!` и вставьте в SteamCMD.
![steamworkshopdownloader.io example steamcmd command](/images/websites/steamworkshopdownloaderio_example_steamcmd_command.png)
4. Необходимый аддон скачался и находится в указанной папке/
</details>
<details>
<summary>

## Распаковка аддона
</summary>

Все необходимые программы можно найти в пункте [Необходимые программы и файлы](#необходимые-программы-и-файлы).

| Тип файла | Необходимая программа |
| --- | --- |
| `*.vpk` | [GCFScape](#2-gcfscape) |
| `*.gma` | [GWTool](#7-gwtool) |

> [!WARNING]
> 
> GCFScape не открывает файлы, у которых в названии есть иероглифы.

* Для распаковки скачанных [`*.vpk`](https://developer.valvesoftware.com/wiki/VPK) файлов можно использовать приложение GCFScape.
* Для распаковки скачанных `*.gma` файлов можно использовать приложение GWTool. Его можно просто запустить и перетащить файл в появившееся окно, после чего оно распакуется в той же папке. (Возможно понадобится `7-Zip` архиватор, для дополнительной распаковки.)
</details>
</details>
<details>
<summary>

# Компиляция `*.mdl` и её особенности
</summary>

Для компиляции необходимо использовать [Crowbar](#1-crowbar). Ссылку на скачивание данной программы можно найти в пункте [необходимые программы и файлы](#необходимые-программы-и-файлы).

Также необходимо настроить Crowbar, при помощи пункта [Настройка программ](#1-crowbar-1).

<details>
<summary>

## Термины
</summary>

Чтобы не было недопонимания напишу сразу термины:
* **Декомпиляция** - это процесс преобразования исполняемого файла обратно в исходный код программы.
* **Компиляция** - это процесс преобразования исходных файлов в исполняемый файл, который будет удобен для программы.

Если простыми словами, то `*.mdl` файл это файл, с которым работает Source Engine.<br>
А `*.smd`, `*.dmx`, `*.vta` и `*.qc` это файлы, которые удобно модифицировать пользователю.
</details>
<details>
<summary>

## Декомпиляция
</summary>

1. Откройте вкладку `Decompile` в приложении Crowbar.
2. В поле `MDL Input:` выберите `File`.
3. В поле `Output to:` выберите `Work folder`.
![Crowbar decompile tab](/images/crowbar/crowbar_decompile_tab.png)
4. Выберите `*.mdl` файл (можно перетащить в поле ввода).
5. Выберите папку, куда будут скидываться исходники модели.
6. Нажмите на кнопку `Decompile`.

> [!WARNING]
>
> Иногда декомпилятор может поломать facepose. Решение этой проблемы будет представлено в пункте [как исправить facepose декомпилятора]()
</details>
<details>
<summary>

## Компиляция
</summary>

1. Откройте вкладку `Compile` в приложении Crowbar.
2. В поле `QC input:` выберите `File`.
3. В поле `Output to:` выбери `Work folder`.
![Crowbar compile tab](/images/crowbar/crowbar_compile_tab.png)
1. Выберите `*.qc` файл (можно перетащить в поле ввода).
2. Выберите папку, куда будут компилироваться файлы в поле ввода `Output to:`.
3. Выберите игру, для которой будете компилировать около надписи `Game that has the model compiler:`.
4. Нажмите на кнопку `Compile`.
</details>
<details>
<summary>

## Как исправить facepose декомпилятора
</summary>

При поломанном facepose некоторые вертиксы не будут дигаться при изменении значения facepose. Выглядет это так:
![Example broken facepose](/images/model/example_broken_facepose.png)

Чтобы исправить facepose необходимо скачать несколько программ, которые можно найти в пункте [необходимые программы и файлы](#необходимые-программы-и-файлы):
* [Blender](#4-blender)
* [Blender Source Tools](#6-blender-source-tools)
* [SourceIO](#10-sourceio)

Нужно будет установить расширения `Blender Source Tools` и `SourceIO` в блендер. Инструкция по установке в пункте [Настройка программ](#настройка-программ).

Чтобы понимать о чём говорится в данном пункте необходимо прочитать пункт [Импорт/экспорт source моделей в Blender]().

Если импортировать `*.qc` при помощи `blender Source Tools` все части модельки вставляются и находятся в одной арматуре. Как это показано на картинке:
<details>
<summary>

### Картинка импорта аддона Blender source tools
</summary>

![Blender source tools import model](/images/blender/blender_source_tools_import_model.png)
</details>

Так как facepose ломает компилятор, то необходимо вставить модельку в blender без использования Crowbar. Для этого можно использовать аддон SourceIO.
<details>
<summary>

### Инструкция по вставке модели через SourceIO
</summary>

1. `File` > `Import` > `Source Engine Assets` > `Source model (.mdl)`
2. ![SourceIO import model toolbar](/images/blender/sourceio_import_model_toolbar.png)
3. Галочки можно не убирать, но `World Scale` надо поставить на `1.0`.
4. ![SourceIO import model menu settings](/images/blender/sourceio_import_model_menu_settings.png)
5. После этого необходимо переименовать все объекты в дереве объектов таким образов: `<name.smd>` > `name`.
![SourceIO import model](/images/blender/sourceio_import_model.png)
6. В результате должно получиться как на [данной картинке](/images/blender/blender_source_tools_import_model.png).
7. После этого facepose будет работать корректно и вы можете продолжить свою работу.
</details>
</details>
</details>
<details>
<summary>

# Необходимые программы и файлы
</summary>

## 1. Crowbar
Ссылка на скачивание программы [Releases · ZeqMacaw/Crowbar](https://github.com/ZeqMacaw/Crowbar/releases).<br>
Это программа для декомпиляции, компиляции и просмотра моделей  на Source и GoldSource с удобным интерфейсом и открытым кодом.<br>
Ссылка на страницу в Valve: [Crowbar - Valve Developer Community](https://developer.valvesoftware.com/w/index.php?title=Crowbar).
## 2. GCFScape
Ссылка на скачивание программы [GCFScape](https://gamebanana.com/tools/26).<br>
GCFScape - это инструмент для просмотра и извлечения файлов из архивов ресурсов игр Quake, GoldSrc и Source.<br>
Ссылка на страницу в Valve: [GCFScape - Valve Developer Community](https://developer.valvesoftware.com/wiki/GCFScape).
## 3. VTFEdit
Ссылка на скачивание программы [VTFLib/VTFEdit v1.3.3](https://gamebanana.com/tools/95).<br>
VTFEdit - инструмент для просмотра, редактирования и создания файлов VTF и VMT.<br>
Ссылка на страницу в Valve: [VTFEdit - Valve Developer Community](https://developer.valvesoftware.com/wiki/VTFEdit).
## 4. Blender
Блендер нужен не ниже версии `2.92`. Не важно Steam версия или с сайта [blender.org](https://www.blender.org/). Ссылки на скачивание:
* blender.org - [Download — blender.org](https://www.blender.org/download/);
* blender.org - 2.92 - [Index of /release/Blender2.92/](https://download.blender.org/release/Blender2.92/);
* Steam - [Blender в Steam](https://store.steampowered.com/app/365670/Blender/).
## 5. default_physics.smd
Файл для корректного регдола модельки. Вы можете скачать данный файл из моего репозитория просто нажав на `<> Code` -> `Download ZIP` или по этой ссылке [default_physics.smd](/files/default_physics.smd).
## 6. Blender Source Tools
Ссылка на скачивание Blender дополнения [Blender Source Tools](http://steamreview.org/BlenderSourceTools/download).<br>
Blender Source Tools добавляют поддержку _Source Engine_ в _Blender_, бесплатный пакет 3D-моделирования. Независимо от того, создаете ли вы простую шляпу или полностью сформулированный персонаж, инструменты Blender Source Tools упрощают экспорт.<br>
Ссылка на страницу в Valve: [Blender Source Tools - Valve Developer Community](https://developer.valvesoftware.com/wiki/Blender_Source_Tools)
## 7. GWTool
Ссылка на скачивание [GWTool](https://github.com/fgblomqvist/gwtool/releases).<br>
Это приложение нужно для распаковки `*.gma` файлов.
## 8. ProportionTrick Script
Ссылка на скачивание [ProportionTrick Script](https://github.com/sksh70/proportion_trick_script).<br>
Это специальный скрипт для создания пропорций моделек.
## 9. 7-Zip
Ссылка на скачивание [7-Zip](https://www.7-zip.org/).<br>
Это приложение нужно для работы с архивами.
## 10. SourceIO
Ссылка на скачивание Blender дополнения [SourceIO](https://github.com/REDxEYE/SourceIO/releases).<br>
Это дополнение, которое позволяет импортировать `*.smd` файлы без декомпиляции их.
</details>
<details>
<summary>

# Настройка программ
</summary>

## 1. Crowbar
Вам необходимо указать путь к `steam.exe`. Для этого нужно открыть вкладку `Set Up Games` и посмотреть нажать на кнопку `Browse...` около текста `Steam executable (steam.exe) [Used for "Run Game" button]:`.  
Если необходио указать путь к игре, то это можно сделать в той же вкладке, выбрав игру в верхнем ComboBox.
## 2. Blender
Чтобы добавить расширение в Blender необходимо сделать следующее:
1. Кнопка `Edit` (около заголовка приложения).
2. Кнопка `Preferences`.
3. Кнопка `Add-ons` (левая часть в открывшемся окне).
4. Кнопка `Install`.
5. Выберите `*.zip` файл с расширением.
6. После загрузки расширения вы сможете его включить нажав на пустой квадратик, чтобы в нём появилась галочка.
![Blender install addons example](/images/blender/install_addons_example.png)
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