# Установка Steamcmd и CS:GO

Обновляет пакеты

```
sudo apt update
```
Установка Screen

```
sudo apt install install screen
```

Установка wget

```
sudo apt install install wget
```

Установка библиотек для Steam

```
sudo apt install lib32stdc++6
```

Создание папок для Steamcmd и CS:GO

```
mkdir ~/steamcmd && mkdir ~/steamcmd/csgo
```

Переход к папке Steamcmd

```
cd ~/steamcmd
```
Скачиваем Steamcmd и распакуем его

```
wget http://media.steampowered.com/client/steamcmd_linux.tar.gz
tar xvfz *.tar.gz
```
Создаем скрипт для установки и обновления CS:GO сервера (Если создали пользователя под другим именем, то необходимо его поменять +force_install_dir /home/*Ваш пользователь*/steamcmd/csgo)

```
echo "STEAMEXE=steamcmd ./steamcmd.sh +force_install_dir /home/csgo/steamcmd/csgo +login anonymous +app_update 740 validate +quit" > updateCSGO.sh
```

Даем право на запуск скрипта

```
chmod +x updateCSGO.sh
```

Запускаем и ждем установку

```
./updateCSGO.sh
```

[Установка Steamcmd и CS:GO](1-steamcmd.md)

