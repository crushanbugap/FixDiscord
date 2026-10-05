<div align="center">

# <img src="https://cdn-icons-png.flaticon.com/128/5968/5968756.png" height=28 /> <a href="https://github.com/crushanbugap/">crushanbugap</a><a href="https://github.com/crushanbugap/zapret-discord-youtube">/zapret-discord-youtube</a> <img src="https://cdn-icons-png.flaticon.com/128/1384/1384060.png" height=28 />

**Новинка:** ускорение Telegram Desktop — https://github.com/crushanbugap/tg-ws-proxy  
Альтернативный вариант — https://github.com/bol-van/zapret-win-bundle  
Поддержать автора оригинального zapret можно [здесь](https://github.com/bol-van/zapret?tab=readme-ov-file#%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D1%82%D1%8C-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0)
</div>

> [!CAUTION]
>
> ### Остерегайтесь подделок
> У меня нет других страниц, Telegram-групп или YouTube-каналов.  
> Любые материалы за пределами этой страницы GitHub, распространяемые от моего имени, являются **ФЕЙКОМ**.

> [!IMPORTANT]
> Исполняемые и системные файлы из каталога [`bin`](./bin) получены из [zapret-win-bundle/zapret-winws](https://github.com/bol-van/zapret-win-bundle/tree/master/zapret-winws) и [релизов zapret](https://github.com/bol-van/zapret/releases). Источник можно проверить по хэшам и контрольным суммам.
>
> #### Всегда проверяйте запускаемые файлы, особенно если скачали их из интернета. Не используйте Яндекс Поиск: среди первых результатов часто встречаются вредоносные файлы, а настоящий репозиторий может быть скрыт.

> [!WARNING]
>
> ### Реакция антивируса
> WinDivert иногда определяется антивирусами.  
> Это необходимый для zapret инструмент перехвата и фильтрации трафика, а не вирус.
> Как и любое средство такого типа, он может применяться как легитимными, так и вредоносными программами.
>
> **Фрагмент [`readme.md`](https://github.com/bol-van/zapret-win-bundle/blob/master/readme.md#%D0%B0%D0%BD%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D1%83%D1%81%D1%8B) проекта [bol-van/zapret-win-bundle](https://github.com/bol-van/zapret-win-bundle)**
>
> Некоторые антивирусы относят WinDivert к инструментам повышенного риска или хакерским средствам, удаляют файлы и помещают их в карантин. Детект обычно называется `WinDivert` или `Not-a-virus:RiskTool.Multi.WinDivert`.
>
> Добавьте каталог zapret в исключения либо отключите обнаружение PUA — потенциально нежелательных приложений. В Kaspersky это, например, настройка «Обнаруживать легальные приложения, которые злоумышленники часто используют для нанесения вреда». Если вы уверенно настраиваете исключения, используйте их; иначе отключите детектирование PUA.

## ⚙️Начало работы

1. Включите Secure DNS.
   * **Chrome:** включите «Использовать безопасный DNS» и выберите поставщика, отличного от «Поставщик по умолчанию».
   * **Firefox:** откройте «DNS через HTTPS», выберите режим «Персональный», затем «Выбрать провайдера/поставщика» и укажите URL вручную. Например: `https://dns.google/dns-query`, поскольку Cloudflare может быть заблокирован.
   * **Windows 11:** Secure DNS можно включить непосредственно в настройках ОС; инструкция доступна [здесь](https://remontka.pro/dns-over-https-windows-11/). Для Windows 11 этот способ рекомендуется.
   * **Keenetic:** включите в настройках роутера «Транзит запросов». Если отключить параметр, Secure DNS на компьютере может работать некорректно.

2. Загрузите zip- или rar-архив с [последнего релиза](https://github.com/crushanbugap/zapret-discord-youtube/releases/latest).

3. В свойствах архива включите «Разблокировать». Для 7-Zip и PeaZip этот шаг не нужен.

4. Распакуйте архив в каталог без кириллицы и специальных символов.

5. Запустите подходящий файл:
   * чтобы подобрать стратегию: **`service.bat`** → `Run Tests` → `Standard tests` → `All configs`;
   * чтобы включить автозапуск: **`service.bat`** → `Install Service` → выберите стратегию.

## ℹ️Файлы и команды

- [**`general.bat ...`**](./general.bat) запускает стратегию вручную. Это удобно для проверки. Результат зависит от множества условий, поэтому перебирайте **`ALT`**, **`FAKE`** и другие варианты, пока не найдёте подходящий.

- [**`service.bat`**](./service.bat) содержит следующие операции:
  - <ins>**`Install Service`** — добавить выбранную стратегию в автозапуск Windows (`services.msc`).</ins>
  - **`Remove Services`** — удалить стратегию и WinDivert из служб.
  - **`Check Status`** — проверить обход, службы автозапуска и WinDivert.
  - **`Game Filter`** — изменить режим для игр и других сервисов, использующих UDP и TCP-порты выше 1023. После изменения перезапустите стратегию. В скобках показывается текущее состояние.
  - **`IPSet Filter`** — включить или отключить обработку ресурсов из `ipset-all.txt`. Это полезно, если ресурс не открывается с zapret, хотя без него работает. Состояния: `none` — IP не проверяются; `loaded` — IP сверяются со списком; `any` — фильтруется любой IP.
  - **`Auto-Update Check`** — включить или выключить автоматический поиск обновлений.
  - **`Replace active fakes`** — заменить используемый fake другим файлом из `bin`.
  - **`Update IPSet List`** — получить актуальный `ipset-all.txt` из репозитория.
  - **`Update Hosts File`** — обновить hosts для исправления веб-версии Telegram и подключения к голосовому чату Discord.
  - **`Check for Updates`** — вручную проверить обновления.
  - **`Run Diagnostics`** — найти распространённые причины неисправности zapret. В конце можно очистить кэш <img src="https://cdn-icons-png.flaticon.com/128/5968/5968756.png" height=11 /> `Discord`.
  - **`Run Tests`** — проверить стратегии:
    - `Standard tests` — сайты из `utils/targets.txt`;
    - `DPI checkers` — DPI у разных провайдеров, включая Cloudflare и Amazon.

## ☑️Частые вопросы

### После запуска `general*` ничего не видно

При запуске стратегии отдельным BAT-файлом, а не через service, должен появиться `winws.exe`, видимый на панели задач. Если его нет, обратитесь к [#522](https://github.com/crushanbugap/zapret-discord-youtube/issues/522).

### Не подходит ни одна стратегия

Откройте командную строку от имени администратора и выполните по очереди:

```cmd
netsh winsock reset
netsh int ip reset all
netsh winhttp reset proxy
ipconfig /flushdns
```

Затем перезагрузите компьютер.

### Не открывается Telegram Web

Откройте **`service.bat`** и выберите **`Update hosts file`**. Если текущий hosts устарел, программа предложит обновить его вручную:

- скопируйте весь текст из открытого блокнота;
- откройте файл `hosts` в появившемся каталоге через редактор, запущенный от имени администратора;
- добавьте скопированное в конец файла либо замените ранее добавленный аналогичный блок;
- сохраните файл и проверьте соединение. Если изменений нет, убедитесь, что hosts действительно сохранён.

#### Работа не гарантируется. Если способ не помог, используйте [Telegram Desktop](https://github.com/telegramdesktop/tdesktop/releases) с [локальным прокси](https://github.com/crushanbugap/tg-ws-proxy) или публичным прокси.

### Обход перестал работать

> [!IMPORTANT]
> Стратегии могут со временем переставать работать после обнаружения. В репозитории есть разные варианты; если ни один не подходит, создайте собственную стратегию на основе существующей, изменив параметры. Описание параметров находится [здесь](https://github.com/bol-van/zapret/blob/master/docs/readme.md#nfqws).

- Проверьте `service.bat` → `Run Diagnostics` на ошибки.
- Убедитесь, что ресурс присутствует в списках доменов или IP.
- Попробуйте **`ALT`**, **`FAKE`** и другие стратегии.
- Выполните полную переустановку по инструкции ниже.
- См. [#765](https://github.com/crushanbugap/zapret-discord-youtube/issues/765).

### Полная переустановка или обновление

1. Сохраните добавленные вами ресурсы и данные.
2. Перезагрузите устройство.
3. Выполните `service.bat` → `Remove Services`.
4. Запустите `service.bat` → `Run Diagnostics`; исправьте ошибки и в конце выберите Y.
5. Удалите старый каталог zapret.
6. Загрузите последнюю версию со [страницы релизов](https://github.com/crushanbugap/zapret-discord-youtube/releases) (`zapret-discord-youtube-...`).
7. Откройте свойства архива правой кнопкой; при наличии «Разблокировать» нажмите её, затем «Применить» и «ОК».
8. Распакуйте архив в новую папку в корне диска, без пробелов и специальных символов.
9. Запускайте разные `general`-скрипты и проверяйте ресурсы. Если стратегия не работает, закройте программу через значок замка на панели задач и попробуйте следующую.
10. После выбора рабочей стратегии включите её автозапуск через `service.bat` → `Install Service`.

### Игра или приложение не работает при включённом zapret

Проверьте, что в `service.bat` параметр `Game Filter` имеет значение **`disabled`**, а `IPSet Filter` — **`none`**. Иначе могут фильтроваться неожиданные ресурсы.

### Античит обнаруживает WinDivert

Инструкция находится в https://github.com/bol-van/zapret-win-bundle/tree/master/windivert-hide.

### Windows 7 требует цифровую подпись WinDivert

Замените `WinDivert.dll` и `WinDivert64.sys` в [`bin`](./bin) одноимёнными файлами из [zapret-win-bundle/win7](https://github.com/bol-van/zapret-win-bundle/tree/master/win7).

### После удаления через `service.bat` WinDivert остался в службах

1. В Windows откройте `cmd` через Win+R и найдите имя службы:

```cmd
driverquery | find "Divert"
```

2. Остановите и удалите её:

```cmd
sc stop название_из_первого_шага
sc delete название_из_первого_шага
```

### Не работает <img src="https://cdn-icons-png.flaticon.com/128/1384/1384060.png" height=18 /> YouTube

- Настройте [Secure DNS](#%EF%B8%8Fначало-работы).
- Отключите блокировщик рекламы: известно, что YouTube начал с ними бороться.
- Переберите остальные стратегии, особенно если раньше всё работало.
- См. [#251](https://github.com/crushanbugap/zapret-discord-youtube/discussions/251).

### Не работает <img src="https://cdn-icons-png.flaticon.com/128/5968/5968756.png" height=18 /> Discord

- Проверьте [Secure DNS](#%EF%B8%8Fначало-работы).
- Сначала определите стратегию, на которой открывается YouTube, и запустите её.
- Через `service.bat` → `Run Diagnostics` очистите кэш Discord.
- Проверьте, помогла ли очистка приложению.
- Откройте https://discord.com/app в браузере. Если веб-версия работает, используйте её.
- Если не работает и браузер, переберите все стратегии: YouTube и Discord могут требовать разные варианты.
- См. [#252](https://github.com/crushanbugap/zapret-discord-youtube/discussions/252).

### Не работает <img src="https://cdn-icons-png.flaticon.com/128/5968/5968804.png" height=18 /> Telegram

Используйте [tg-ws-proxy](https://github.com/crushanbugap/tg-ws-proxy) или бесплатные MTProto-прокси из интернета.

### Не работают игры

У игр разные требования, поэтому проверить и исправить каждую невозможно. Универсальный порядок действий:

- через `service.bat` обновите ipset и включите `Game Filter`;
- при отсутствии результата дополнительно включите `ipset any`.

`ipset any` может нарушить открытие многих сайтов, поэтому не оставляйте его включённым постоянно. Определите IP игры и внесите их в `ipset-all.txt`.

Если это не помогло, создайте обсуждение в [Discussions](https://github.com/crushanbugap/zapret-discord-youtube/discussions), а не issue, и дождитесь помощи других игроков.

### Проблема не описана

Создайте обращение [здесь](https://github.com/crushanbugap/zapret-discord-youtube/issues).

## 🗒️Добавление других адресов

Расширить список ресурсов можно через следующие файлы:

- **`list-general-user.txt`** — домены; поддомены учитываются автоматически;
- **`list-exclude-user.txt`** — домены-исключения, например когда IP сети есть в `ipset-all.txt`, но конкретный домен фильтровать не нужно;
- **`ipset-all.txt`** — IP-адреса и подсети;
- **`ipset-exclude-user.txt`** — исключаемые IP и подсети.

Файлы **`*-user.txt`** создаются автоматически при первом запуске `zapret` или `service.bat`.

## ⭐Поддержка

Поставьте :star: этому репозиторию в правом верхнем углу страницы.

Финансово поддержать разработчика оригинального zapret можно [здесь](https://github.com/bol-van/zapret?tab=readme-ov-file#%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D1%82%D1%8C-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0).

## ⚖️Лицензия

Проект распространяется по лицензии [MIT](https://github.com/crushanbugap/zapret-discord-youtube/blob/main/LICENSE.txt).

## 🩷Участники

[![Contributors](https://contrib.rocks/image?repo=crushanbugap/zapret-discord-youtube)](https://github.com/crushanbugap/zapret-discord-youtube/graphs/contributors)

💖 Спасибо разработчику [zapret](https://github.com/bol-van/zapret) — [bol-van](https://github.com/bol-van).