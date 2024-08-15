![image](https://github.com/user-attachments/assets/425c8f0c-de43-4325-ac15-5abe1b27cfdd)

![image](https://github.com/user-attachments/assets/75e5f990-50b2-4b27-a213-b1b1e0393fcc)

![image](https://github.com/user-attachments/assets/9db50d61-fc06-48fa-bb28-bf172399b9ef)

**ВЫПОЛНЕНИЕ** 

**Часть 1. Настройка основного сетевого устройства**

**Шаг 1. Создайте сеть.**

![image](https://github.com/user-attachments/assets/0aa27dbb-5284-476f-a414-869790314f27)

**Шаг 2. Настройте маршрутизатор R1.**

a.	Загрузите следующий конфигурационный скрипт на R1.

![image](https://github.com/user-attachments/assets/7f149ae5-5409-409f-9a0b-5b0a2ab0f589)

![image](https://github.com/user-attachments/assets/c0815bab-d0c0-45d0-ad0a-7638a4fc7d16)

**Шаг 3. Настройка и проверка основных параметров коммутатора**

a.	Настройте имя хоста для коммутаторов S1 и S2.

b.	Запретите нежелательный поиск в DNS.

c.	Настройте описания интерфейса для портов, которые используются в S1 и S2.

d.	Установите для шлюза по умолчанию для VLAN управления значение 192.168.10.1 на обоих коммутаторах.

![image](https://github.com/user-attachments/assets/5487d369-af45-4a34-a36a-ca9b069a87f4)

![image](https://github.com/user-attachments/assets/2a92c215-9307-4c1f-a662-c37afe846358)

![image](https://github.com/user-attachments/assets/e9d47060-8aa9-4a09-984c-eee751e8e82c)

![image](https://github.com/user-attachments/assets/23ff83bc-a585-4dc8-af1d-076859541c53)

![image](https://github.com/user-attachments/assets/bc5feff6-8e79-457c-93df-969dbd3f81e2)

![image](https://github.com/user-attachments/assets/04560b0c-a86c-4fd8-9197-e5e98b50bdeb)

**Часть 2. Настройка сетей VLAN на коммутаторах.**

**Шаг 1. Сконфигруриуйте VLAN 10.**

Добавьте VLAN 10 на S1 и S2 и назовите VLAN - Management.

**Шаг 2. Сконфигруриуйте SVI для VLAN 10.**

Настройте IP-адрес в соответствии с таблицей адресации для SVI для VLAN 10 на S1 и S2. Включите интерфейсы SVI и предоставьте описание для интерфейса.

**Шаг 3. Настройте VLAN 333 с именем Native на S1 и S2.**

**Шаг 4. Настройте VLAN 999 с именем ParkingLot на S1 и S2.**






