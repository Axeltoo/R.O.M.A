<h1 align="center">
  <a href="https://youtu.be/SoLUaoV-Cu4"><img src="https://github.com/Axeltoo/R.O.M.A/blob/main/FgMEpQa9who.jpg" alt="Робот от команды LH MIREA" width="800"></a>
  <br>
	Робот от команды LH MIREA
  <br>
</h1>


## Основные детали
* usb-разветвитель или преобразователь логических уровней;
* usb-ttl преобразователь;
* XL4005 dc/dc преобразователь;  
* arduino uno;
* MX1508 драйвер двигателей;
* 4x желтые ардуино TT-мотор-редукторы;
* 2x 18650 аккумуляторы и батарейный отсек для них;
* тумблер;

## Настройка Orange pi

### Подключаемся к точке доступа
```shell
sudo armbian-config
```
Переходим в **Network->WiFi**, выбираем нужную точку доступа,
вводим пароль и подключаемся к ней.    
Чтобы узнать свой ip-адресс вводим 
```shell
ifconfig
```

### Установка зависимостей
Обновляемся:
```shell
sudo apt update
sudo apt upgrade
```
Загружаем питоновый менеджер пакетов и вспомогательные пакеты
```shell
sudo apt install python3-dev python3-pip python3-numpy
```
Загружаем еще немного зависимостей
```shell
pip3 install --upgrade pip setuptools wheel
pip3 install flask pyserial 
```
Загружаем openCV
```shell
sudo apt install python3-opencv
```

### Запуск приложения
Скачиваем репозиторий проекта
```shell
git clone https://github.com/TrashRobotics/CVbot
```
и запускаем приложение
```shell
cd CVbot/python_app
python3 app.py -i (ip-адресс orange pi) -p (порт) -s (последовательный порт)
```
Открываем браузер и вводим в нем 
```shell
(ip-адресс orange pi):(порт)
```
Например так:
```shell
192.168.42.1:5000
```     

Подробнее про все остальное смотрите в видео
