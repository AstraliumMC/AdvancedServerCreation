![AstGuide.png](https://i.imgur.com/vQ8j1NO.png)

# Дополнительная информация о данном LegacyInfo.md
```
Здесь будут опубликованы неактуальные команды/утилиты, чтобы не засорять основной README.md

Данная статья рассчитана на настройку под Ubuntu (рекомендуется) / Debian.
В случае если у вас Arch Linux или другие UNIX подобные системы - Ознакомьтесь с репозиторием необходимых пакетов.
Если необходимые пакеты отсутствуют, то попробуйте найти их в AUR/Snap/Flatpak.
В случае с AUR изучайте билд скрипт для вашей же безопасности.

Некоторые функции могут не работать конкретно на вашей системе. В этом случае не нужно винить автора статьи.
За подробной поддержкой обращайтесь в мой дискорд Astralium Org. - https://discord.gg/7XkGYJbtZg
```

### Специально для CentOS 8 (Не поддерживается автором статьи)
```
yum

yum update

yum upgrade

dnf

sudo dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm

dnf install htop

dnf install screen
```

### Oracle Cloud установка под Minecraft
```
# Использование с UFW утилитой
sudo ufw enable # <- По умолчанию он выключен, поэтому его следует включить.
sudo ufw allow 25565 comment "Данный порт открыт по UDP/TCP протоколам для всех входящих соединений"
sudo ufw reload # <- На всякий случай.

# Использование с FIREWALLD утилитой
sudo apt install firewalld # <- Установка пакета не требуется, если вы установили его в начале этой статьи.
sudo firewall-cmd --permanent --zone=public --add-port=25565/tcp
sudo firewall-cmd --permanent --zone=public --add-port=25565/udp
sudo firewall-cmd --reload # <- Обычно он всегда требует перезагрузки для того, чтобы новые правила вступили в силу.

# < ! > Обратите особое внимание во избежание утраты доступа к вашей Linux машине < ! >
# По умолчанию FIREWALLD и UFW утилиты закрывают все порты, конечно в них имеются исключения для 22/tcp порта,
# Однако в любом случае рекомендуется вручную открыть OpenSSH порт.
# Использование в UFW и FIREWALLD:

# sudo ufw allow 22/tcp comment "Порт для использования удалённого подключения к данной машине по SSH протоколу"
# sudo firewall-cmd --permanent --zone=public --add-port=25565/tcp
# sudo firewall-cmd --reload # <- Обычно он всегда требует перезагрузки для того, чтобы новые правила вступили в силу.

```

### "WinRar" - Известный архиватор, но для Linux (Лучше использовать tar)
```
# Установка
apt install zip unzip

# Там где нужно будет создать архив - у меня это папку /home
cd home

# Архивирование папки/файла | Можно находиться в любом пути (Вы указываете конкретно путь до папки/файла , который нужно заархивировать)
zip -r NAME.zip /home/BungeeCord

# Для примера в моем случае
# /home - дирректория папки с сервером
# /BungeeCord - сама папка с банджей, можно любую например: Survival, Anarchy, SkyBlock.

zip -r surv.zip /home/Survival

# Если имеется SkyBlock папка с сервером, то введите эту команду
# Указывать можно любой сервер, также вы можете например хранить сервер по пути /servers/BungeeCord
# Не обязательно использовать /home раздел для серверов!

zip -r sb.zip /home/SkyBlock

# Либо используйте встроенный tar
```