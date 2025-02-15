**Лабораторная работа. Просмотр таблицы MAC-адресов коммутатора** 

**Топология**
 
![image](https://github.com/larakor/Network-/assets/164779961/28fde916-6862-46de-89bf-046710a11f4e)


**Таблица адресации**

![image](https://github.com/larakor/Network-/assets/164779961/55823ddc-117f-4bb5-bf31-7d00914ee7b9)


**Часть 1. Создание и настройка сети**

**Часть 2. Изучение таблицы МАС-адресов коммутатора**

Необходимые ресурсы:
 
•	2 коммутатора (Cisco 2960 с операционной системой Cisco IOS 15.2(2) (образ lanbasek9) или аналогичная модель)

•	2 ПК (Windows и программа эмуляции терминала, такая как Tera Term)

•	Консольные кабели для настройки устройств Cisco IOS через консольные порты.

•	Кабели Ethernet, расположенные в соответствии с топологией

Примечание. Интерфейсы Fast Ethernet на коммутаторах Cisco 2960 определяют тип подключения автоматически, поэтому между коммутаторами S1 и S2 можно использовать прямой кабель Ethernet. При использовании коммутатора Cisco другой модели может потребоваться перекрестный кабель Ethernet.

**ВЫПОЛНЕНИЕ**

**Часть 1. Создание и настройка сети**

**Шаг 1. Подключите сеть в соответствии с топологией.**

![image](https://github.com/larakor/Network-/assets/164779961/b4056b68-15b5-46cc-912f-7fd9bfa85211)

**Шаг 2. Настройте узлы ПК.**

![image](https://github.com/larakor/Network-/assets/164779961/55193ddb-5449-4c8e-93a4-0be9eeda72d7)

![image](https://github.com/larakor/Network-/assets/164779961/05a7eea3-25ee-47a3-9c36-5f6b00512a37)

**Шаг 3. Выполните инициализацию и перезагрузку коммутаторов.**

На обоих коммутаторах сделали:

![image](https://github.com/larakor/Network-/assets/164779961/d9d74329-3dfc-42f9-9d41-0b5ea31e004a)


**Шаг 4. Настройте базовые параметры каждого коммутатора.**

Откройте окно конфигурации

a.	Настройте имена устройств в соответствии с топологией.

b.	Настройте IP-адреса, как указано в таблице адресации.

c.	Назначьте cisco в качестве паролей консоли и VTY.

d.	Назначьте class в качестве пароля доступа к привилегированному режиму EXEC.

Для S1:

![image](https://github.com/larakor/Network-/assets/164779961/dc4fa0a9-9c2a-4bc7-a948-07bed54b1813)

Для S2:

![image](https://github.com/larakor/Network-/assets/164779961/9da91021-4cff-4f76-8553-8cba752ae884)

**Часть 2. Изучение таблицы МАС-адресов коммутатора**

**Шаг 1. Запишите МАС-адреса сетевых устройств.**

a.	Откройте командную строку на PC-A и PC-B и введите команду ipconfig /all.

Открытие окна командной строки Windows
Вопрос:

Назовите физические адреса адаптера Ethernet.

**MAC-адрес компьютера PC-A:** 

C:\>ipconfig /all

FastEthernet0 Connection:(default port)

Connection-specific DNS Suffix..: 
Physical Address................: 00E0.8FC3.492D

**MAC-адрес компьютера PC-B:**
C:\>ipconfig /all

FastEthernet0 Connection:(default port)

Connection-specific DNS Suffix..: 
Physical Address................: 0001.C9CA.3941


b.	Подключитесь к коммутаторам S1 и S2 через консоль и введите команду show interface F0/1 на каждом коммутаторе.
Откройте окно конфигурации

Вопросы:
Назовите адреса оборудования во второй строке выходных данных команды (или зашитый адрес — bia).

**МАС-адрес коммутатора S1 Fast Ethernet 0/1:**

S1#show interface F0/1 
FastEthernet0/1 is up, line protocol is up (connected)
Hardware is Lance, address is 0001.974e.9c01 (bia 0001.974e.9c01)

**МАС-адрес коммутатора S2 Fast Ethernet 0/1:**

S2#show interface F0/1
FastEthernet0/1 is up, line protocol is up (connected)
Hardware is Lance, address is 00e0.f9a0.9001 (bia 00e0.f9a0.9001)

Закройте окно настройки.

**Шаг 2. Просмотрите таблицу МАС-адресов коммутатора.**

a.	Подключитесь к коммутатору S2 через консоль и войдите в привилегированный режим EXEC.
Откройте окно конфигурации

b.	В привилегированном режиме EXEC введите команду show mac address-table и нажмите клавишу ввода.

S2# show mac address-table

![image](https://github.com/larakor/Network-/assets/164779961/b7070fee-00e7-477f-8e69-892a1a2b10f8)

После пинга в таблице мас адресов добавляются адреса всех покдлючений

![image](https://github.com/larakor/Network-/assets/164779961/6a1ab08e-cb24-4708-bb6d-3fdc5969bf81)

Если вы не записали МАС-адреса сетевых устройств в шаге 1, как можно определить, каким устройствам принадлежат МАС-адреса, используя только выходные данные команды show mac address-table? – по интерфейсу. Работает ли это решение в любой ситуации? – бывает, что с одним портом связны несколько мас адресов

**Шаг 3. Очистите таблицу МАС-адресов коммутатора S2 и снова отобразите таблицу МАС-адресов.**

a.	В привилегированном режиме EXEC введите команду clear mac address-table dynamic и нажмите клавишу Enter.
S2# clear mac address-table dynamic

b.	Снова быстро введите команду show mac address-table.

![image](https://github.com/larakor/Network-/assets/164779961/b5cdcb19-010d-43b6-b151-627a2156013a)

Указаны ли в таблице МАС-адресов адреса для VLAN 1? Указаны ли другие МАС-адреса?- нет
Через 10 секунд введите команду show mac address-table и нажмите клавишу ввода. Появились ли в таблице МАС-адресов новые адреса? - нет

 
**Шаг 4. С компьютера PC-B отправьте эхо-запросы устройствам в сети и просмотрите таблицу МАС-адресов коммутатора.**

a.	На компьютере PC-B откройте командную строку и еще раз введите команду arp -a.

![image](https://github.com/larakor/Network-/assets/164779961/9c07ddf9-7db1-418d-9831-a2fd6116f0f1)

b.	Из командной строки PC-B отправьте эхо-запросы на компьютер PC-A, а также коммутаторы S1 и S2.

![image](https://github.com/larakor/Network-/assets/164779961/db69ac3d-678d-403d-b3bd-639b4af0b9db)

c.	Подключившись через консоль к коммутатору S2, введите команду show mac address-table.

![image](https://github.com/larakor/Network-/assets/164779961/99c93cca-2502-4c6a-ab21-6172aab829bf)

Добавились в таблицу МАС-адресов адреса PC-A, PC-B, S1 F0/1, S1 Vlan1

На компьютере PC-B откройте командную строку и еще раз введите команду arp -a.

![image](https://github.com/larakor/Network-/assets/164779961/b300416c-5585-49b3-a33a-1bec3f54dc06)

Появились ли в ARP-кэше компьютера PC-B дополнительные записи для всех сетевых устройств, которым были отправлены эхо-запросы? - да





