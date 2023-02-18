# Установка Metamod и SourceMod

Переходим в папку csgo

```
cd csgo
```

Скачиваем Metamod 

```
wget https://mms.alliedmods.net/mmsdrop/1.11/mmsource-1.11.0-git1148-linux.tar.gz
```

Скачиваем SourceMod

```
wget https://sm.alliedmods.net/smdrop/1.11/sourcemod-1.11.0-git6931-linux.tar.gz
```

Распакуем 

```
tar xvfz mmsource-1.11.0-git1148-linux.tar.gz.tar.gz
tar xvfz sourcemod-1.11.0-git6931-linux.tar.gz
```

Перейдем в папку с конфигами

```
cd addons/sourcemod/configs
```

Настроим админку 

```
nano *.ini
```

В самом конце добавим Steam ID <br/> (Указывайте свой steam id)

```
"STEAM_1:1:597467377" "99:z"
```

Сохраняем! <br/> Настроим core.cfg

```
nano core.cfg
```

Находим BlockBadPlugins и меняем на "no" 

```
 /**
         * Enables or disables whether SourceMod blocks known or potentially ma>
         * It is STRONGLY advised that this is left enabled, there have been ca>
         * allow anyone to delete files on the server, gain full rcon control, >
         *
         * "yes"        - Block malware or illegal plugins from loading (defaul>
         * "no"         - Warn about malware or illegal plugins loading
         */
        "BlockBadPlugins"       "no"
```

Находим FollowCSGOServerGuidelines и меняем на "no" 

```
/**
         * Per "http://blog.counter-strike.net/index.php/server_guidelines/", c>
         * functionality will trigger all of the game server owner's Game Serve>
         * (GSLTs) to get banned when executed on a Counter-Strike: Global Offe>
         *
         * Enabling this option will block plugins from using functionality tha>
         * This option only has any effect on CS:GO. Note that this does NOT gu>
         * receive a ban.
         *
         * Disable this option at your own risk.
         */
        "FollowCSGOServerGuidelines"    "no"
```

Переходим обратно

```
cd ~/steamcmd/csgo/csgo/addons/sourcemod/plugins
```

Уберем лишние плагины (Я делаю так)

```
for file in `ls  | egrep -v "admin-flatfile.smx|basecommands.smx|disabled"` ; do mv $file disabled/ ; done
```
[Установка других плагинов](4-plugins.md)
