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
##### 3. Установите RDP:
```
sudo apt install xrdp xorgxrdp
```
##### 4. Настраиваете RDP на своей винде:

![Ищете прогу](https://github.com/Sanlut/Nym/blob/main/999.png)

##### 5. 

https://github.com/nymtech/nym/releases/tag/v0.12.0


```
chmod a+x ~/Downloads/nym-wallet_0.12.0_ubuntu_20.04_amd64.AppImage
```
```
~/Downloads/nym-wallet_0.12.0_ubuntu_20.04_amd64.AppImage
```

2.	создаем новый каталог в котором будет лежать файл ноды
```
mkdir nym
```
3.	переходим в этот каталог
```
cd nym
```
4.	качаем скомпилированную версию ноды с гитхаба 
```
wget https://github.com/nymtech/nym/releases/download/v0.12.0/nym-mixnode
```
5.	назначем права доступ файлу
```
chmod 755 nym-mixnode
```
7.	инициализируем ноду. Тут ВНИМАНИЕ! Нужно ввести свой идентификатор ноды (любоё имя) и адрес своего кошелька 
```
./nym-mixnode init --id gaimepex --host $(curl ifconfig.me) --wallet-address nymt1v3v888pphfhja4kn998w6592vz00cvfdd066lc
```
