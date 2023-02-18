# Насройка CFG

Предварительная настройка

```
cd ~/.steam/
```
```
mkdir sdk32
```
```
ln -s /home/csgo/steamcmd/linux32/steamclient.so /home/csgo/.steam/sdk32/
```

Переходим в папку с сервером

```
cd ~/steamcmd/csgo
```

Создаем скрипт для запуска сервера

```
printf 'screen -A -m -d -S server ./srcds_run -game csgo -console -usercon +game_type 0 +game_mode 1 +map de_mirage -tickrate 128 -ip 0.0.0.0 +net_public_adr *Ваш IP* -port 27015 -maxplayers_override 16 +fps_max 0' > start.sh
```

Даем право на запус скрипта

```
chmod +x start.sh
```

Переходим в папку csgo

```
cd csgo
```

Создаем файл с API стим аккаунта

```
nano webapi_authkey.txt
```

И ставим туда API ключ от аккаунта Steam https://steamcommunity.com/dev/apikey (Чтобы сохранить ctrl + o, enter, ctrl + x) Пример:

```
VTA9SYK5GJE2PR23FSPGUGQW5TUZYT36
```

Переходим в папку cfg

```
cd cfg
```

Создаем файл server.cfg

```
nano server.cfg
```

Мой cfg выглядит так (Чтобы сохранить ctrl + o, enter, ctrl + x)

```
hostname "n0maCi" // Название сервера
rcon_password "" // Задает пароль от rcon
sv_password "" // Задает пароль от сервера
sv_region "255" // Задает регион сервера
sv_setsteamaccount "VTA9SYK5GJE2PR23FSPGUGQW5TUZYT36" // Токен для запуска сервра, получить можно тут: https://steamcommunity.com/dev/managegameservers
sv_pure "0"
sv_maxrate "786432"
sv_mincmdrate "128"
sv_minrate "128000"
sv_minupdaterate "128"
sv_client_cmdrate_difference "0"
```

Все готово для первого запуска! Переходи к изначальной папке

```
cd ~/steamcmd/csgo
```

Запускаем

```
./start.sh
```

Чтобы увидеть консоль нужно прописать (Для выхода из консоли нужно нажимать: ctrl + a + d)

```
screen -R server
```

Присоединяемся к серверу

```
connect *ВАШ IP*:27015
```

Если ставили пароль, то надо так:

```
connect *ВАШ IP*:27015;password *ВАШ ПАРОЛЬ*
```
Если все нормальн, то закрываем сервер и переходим к след. шагу

```
exit
```
