# vix

декларативный менеджер для Void Linux

### Команды
<img width="868" height="308" alt="изображение" src="https://github.com/user-attachments/assets/75ecf3c5-78c5-464e-af07-d11e9d36153d" />


VIX - уникальный декларативный менеджер состояния системы. Он позволяет декларативно менять пакеты, сервисы, репозитории, дотфайлсы и любую другую вашу папку по вышему усмотрению. Управление происходит в папке с декларативными конфигами config.vix
<img width="531" height="231" alt="изображение" src="https://github.com/user-attachments/assets/2fcf4d22-0604-4961-a750-62474aed663d" />

*config.vix*

#### В dotfiles лежат дотфайлы из .config, файлы из home начинающиеся с точки (типа .Xresources)
<img width="587" height="876" alt="изображение" src="https://github.com/user-attachments/assets/1ada51d9-7aaf-40c3-9097-853a888774c9" />

#### В packages.vix список всех пакетов, которые можно удалять и устанавливать, меняя файл
<img width="460" height="390" alt="изображение" src="https://github.com/user-attachments/assets/d67f4bad-c9cb-40b9-9869-b3cb7b7a1980" />

*packages.vix*

#### В services.vix список сервисов,
который парсится из папок var/service и etc/sv, сервисы можно удалять (удаляя строчку из любого из 2 разделов папка сервиса удаляется), отключать и включать внутри /var/service и создавать симлинки из etc/sv в var/service путём переноса строчки из второго раздела в первый

<img width="460" height="393" alt="изображение" src="https://github.com/user-attachments/assets/fde867d3-b2cf-4ae9-86dd-7d2a64d3721a" />

*services.vix*

#### repo.vix - парсит файлы с репозиториями, системные из usr/share/xbps.d и пользовательские из etc/xbps.d

<img width="652" height="294" alt="изображение" src="https://github.com/user-attachments/assets/4d600f3b-03d9-4577-9c92-70bf8494e8e0" />

*repo.vix*

#### Папка store хранит слепки, по умолчанию последние 30, можно изменить в начале кода vix

<img width="168" height="55" alt="изображение" src="https://github.com/user-attachments/assets/dcad1ef7-51c1-41ad-8f2d-ae407eee66f0" />

*vix*

<img width="553" height="302" alt="изображение" src="https://github.com/user-attachments/assets/52210167-1f7d-4cda-8c97-0d3ab576d81c" />

*config.vix/store*

## Что делают команды?

`sync` - синхронизирует императивное состояние системы с декларативными конфигами в ~/config.vix. Если такой папки не было создаёт её, подходит для первичной установки

`switch`, `s` - наоборот, синхронизирует изменения из декларативной папки config.vix в реальную систему. Устанавливает или удаляет пакеты, изменяет сервисы, репозитории, донтфайлы и доп папки, и создаёт **слепок**

`list`, `l` - посмотреть список всех слепков

 `rollback`, `r` - откатиться до одного из старых слепков по его номеру или хэшу

 `add`, `a` - добавить в декларативную папку любую свою папку, которую вы хотите декларативно синхронизировать
