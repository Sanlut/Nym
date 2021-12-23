# Nym
### Создаем ноду 12.0 с графич. оболочкой с досдупом по РДП

##### 1. Обновите пакеты:
```
sudo apt update && sudo apt upgrade -y
```
##### 2. Установите графическую оболочку:
```
sudo apt install ubuntu-desktop
```
```
sudo apt install xfce4 xfce4-goodies xorg dbus-x11 x11-xserver-utils
```
Во время установки я всегда выбирал этот второй параметр. Хз просто в первую установку в него нажал... работает, потому первый в другие разы и непробовал

![](https://github.com/Sanlut/Nym/blob/main/ubuntu1.png)

##### 3. Установите RDP:
```
sudo apt install xrdp xorgxrdp
```

На ноде пока все. Как закончилась установка, переходим к себе в винду, подключаемся к граф. интерфесу ноды, шаманим там. Потом, когда установим кошелек, врнемся сюда устанавливать ноду.

##### 4. Настраиваете RDP на своей винде:
4.1. Ищете через пуск
![Ищете прогу](https://github.com/Sanlut/Nym/blob/main/999.png)

4.2. Запускаете, прописываете ip впски и пользователя `root`. Если нод несколько, то можете сохранить ярлык отдельный для каждой ноды

![Прописываем параметры и запускаем](https://github.com/Sanlut/Nym/blob/main/rdp.png)

##### 5. Настраиваете Ubuntu и кошелек, бондите ноду

5.1. Сразу после входа в бубунту и отвечание на всякие тупые вопросы, тыцаете в Активитис

![](https://github.com/Sanlut/Nym/blob/main/firefox.png)

Запускаете файрфокс, чтобы выбраться в инет

5.2. Скачиваем кошелек по этой ссылке

https://github.com/nymtech/nym/releases/tag/v0.12.0

![](https://github.com/Sanlut/Nym/blob/main/wal.png)

5.3. Запускаем терминал в бубунте

![](https://github.com/Sanlut/Nym/blob/main/term1.png)

5.4. Вводим поочередно след. команды и запускаем так кошель

```
chmod a+x ~/Downloads/nym-wallet_0.12.0_ubuntu_20.04_amd64.AppImage
```
```
~/Downloads/nym-wallet_0.12.0_ubuntu_20.04_amd64.AppImage
```

![](https://github.com/Sanlut/Nym/blob/main/term2.png)

Кошелек запустился. Поздравляю - вы охуевший хацкер.
В кошеле все понятно. Разберетесь без инструкции. Тут пока все. Возвращаемся в PuTTY и подымаем саму ноду. Потом вернемся сюда в кошель, чтоб забондить ее.

##### 6.	Подымаете ноту в PuTTY

6.1.	Создаем новый каталог в котором будет лежать файл ноды
```
mkdir nym
```

6.2.	Переходим в этот каталог

```
cd nym
```

6.3.	Качаем скомпилированную версию ноды с гитхаба 

```
wget https://github.com/nymtech/nym/releases/download/v0.12.0/nym-mixnode
```

6.4.	Назначем права доступа к файлу

```
chmod 755 nym-mixnode
```

6.5.	Инициализируем ноду. Тут ВНИМАНИЕ! Нужно ввести свой идентификатор ноды (имя старой ноды я вводил) и адрес своего кошелька 

```
./nym-mixnode init --id ИМЯНОДЫ --host $(curl ifconfig.me) --wallet-address nymхххххххХХХХхХХХхххххх
```
6.6. Копируем в блокнот текст, который после этого появится:

    Initialising mixnode ИМЯНОДЫ...
    Saved mixnet identity and sphinx keypairs
    Saved configuration file to "/root/.nym/mixnodes/sanlut/config/config.toml"
    Mixnode configuration completed.

    Identity Key: FvaiAFifqCh37KNqjvcQGmWAuMyd6aUVfx6rcdQjwvmT
    Sphinx Key: 7Nc5BKSpRUWtDZZXCZJ21DUMgTa8rDAzXAAVHMu1ucsZ
    Owner Signature: 3eczkay2FpRoUyLZnTzAq3GkBkHWaquhApdJdM2akaFS3h5xGxvHVaxBTYJLwnAmakjUk4wTv764FnuYp9EKzEr
    Host: 65.108.182.19 (bind address: 65.108.182.19)
    Version: 0.12.0
    Mix Port: 1789, Verloc port: 1790, Http Port: 8000

    You are bonding to wallet address: nymхххххххХХХХхХХХхххххх

##### 7. Возвращаемся в бубунту через RDP, где у нас кошель, и там бондим эту ноду, введя в соответствующие поля все вот это, что выше вам дали


