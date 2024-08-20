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

![image](https://github.com/user-attachments/assets/277642a7-8560-4fd1-ab50-b33586433533)

![image](https://github.com/user-attachments/assets/dd9c343c-a640-477d-a082-806e5e6cd04f)

![image](https://github.com/user-attachments/assets/2af8a7ff-5359-4130-8535-000cca4d7e2b)

**Часть 3. Настройки безопасности коммутатора.**

**Шаг 1. Релизация магистральных соединений 802.1Q.**

a.	Настройте все магистральные порты Fa0/1 на обоих коммутаторах для использования VLAN 333 в качестве native VLAN.

b.	Убедитесь, что режим транкинга успешно настроен на всех коммутаторах.
S1# show interface trunk

![image](https://github.com/user-attachments/assets/5e647a65-f22d-4eef-a734-02deffa83778)

![image](https://github.com/user-attachments/assets/10cb36d4-2e78-4bb2-852f-ba31093d0b17)

![image](https://github.com/user-attachments/assets/a904b0fd-8156-448b-a9ca-354640508092)

c.	Отключить согласование DTP F0/1 на S1 и S2. 

d.	Проверьте с помощью команды show interfaces.

![image](https://github.com/user-attachments/assets/17af4dd4-0621-487c-9449-1835e01cdd6d)

![image](https://github.com/user-attachments/assets/1669cb74-a6fb-4b67-94e9-c475b6523791)

**Шаг 2. Настройка портов доступа**

a.	На S1 настройте F0/5 и F0/6 в качестве портов доступа и свяжите их с VLAN 10.

![image](https://github.com/user-attachments/assets/aa0ae08c-d367-4201-9a0a-edb2369a0167)

b.	На S2 настройте порт доступа Fa0/18 и свяжите его с VLAN 10.

![image](https://github.com/user-attachments/assets/285886df-0b0e-45a8-acfe-2d27edc7ba6b)

**Шаг 3. Безопасность неиспользуемых портов коммутатора**

a.	На S1 и S2 переместите неиспользуемые порты из VLAN 1 в VLAN 999 и отключите неиспользуемые порты.

![image](https://github.com/user-attachments/assets/e5a36ff6-7b23-453e-a5d8-fc6f8df0b82a)

![image](https://github.com/user-attachments/assets/688c9928-642c-4723-b26a-997e43c6d077)

b.	Убедитесь, что неиспользуемые порты отключены и связаны с VLAN 999, введя команду  show.

![image](https://github.com/user-attachments/assets/67ea96f0-739d-407e-8557-db6a1883121a)

![image](https://github.com/user-attachments/assets/24bf09c4-d68d-49e1-8efa-2fac9d191cb6)

**Шаг 4. Документирование и реализация функций безопасности порта.**

a.	На S1, введите команду show port-security interface f0/6  для отображения настроек по умолчанию безопасности порта для интерфейса F0/6. 

![image](https://github.com/user-attachments/assets/9ef3b2b9-0f7f-46b4-a8c6-5a8973072c2d)

b.	На S1 включите защиту порта на F0 / 6 со следующими настройками:

o	Максимальное количество записей MAC-адресов: 3

o	Режим безопасности: restrict

o	Aging time: 60 мин.

o	Aging type: неактивный

![image](https://github.com/user-attachments/assets/dbb4d2a4-1f37-4d45-b45c-905feb2a4a90)

Последняя команда не поддерживается

c.	Verify port security on S1 F0/6. S1# show port-security interface f0/6    S1# show port-security address

![image](https://github.com/user-attachments/assets/77ce7c2a-7a36-4708-a07c-08e189e2faa6)

d.	Включите безопасность порта для F0 / 18 на S2. Настройте каждый активный порт доступа таким образом, чтобы он автоматически добавлял адреса МАС, изученные на этом порту, в текущую конфигурацию.

![image](https://github.com/user-attachments/assets/5b40d24d-0174-40d3-b6d1-eb6b2ab19287)

e.	Настройте следующие параметры безопасности порта на S2 F / 18:

o	Максимальное количество записей MAC-адресов: 2

o	Тип безопасности: Protect

o	Aging time: 60 мин.

![image](https://github.com/user-attachments/assets/e792cf5e-625b-48b7-b10e-5a9ddee3eb65)

f.	Проверка функции безопасности портов на S2 F0/18.  S2# show port-security interface f0/18    S2# show port-security address

![image](https://github.com/user-attachments/assets/ea7e8ff9-c768-400a-8b30-7ae25b656aa5)


**Шаг 5. Реализовать безопасность DHCP snooping.**

a.	На S2 включите DHCP snooping и настройте DHCP snooping во VLAN 10.

b.	Настройте магистральные порты на S2 как доверенные порты.

c.	Ограничьте ненадежный порт Fa0/18 на S2 пятью DHCP-пакетами в секунду.

d.	Проверка DHCP Snooping на S2.  S2# show ip dhcp snooping

![image](https://github.com/user-attachments/assets/1f35e7c5-62a0-4520-8886-5d97a3cf704d)

e.	В командной строке на PC-B освободите, а затем обновите IP-адрес.

![image](https://github.com/user-attachments/assets/90a6cd7f-f98f-45b9-8008-e75e748c68ac)

C:\Users\Student> ipconfig /release

C:\Users\Student> ipconfig /renew

![image](https://github.com/user-attachments/assets/e94a1565-96ae-4626-962d-20df3213e4e2)

f.	Проверьте привязку отслеживания DHCP с помощью команды show ip dhcp snooping binding.  S2# show ip dhcp snooping binding 

![image](https://github.com/user-attachments/assets/1715402d-f96c-4300-b018-908bb6645308)

**Шаг 6. Реализация PortFast и BPDU Guard**

a.	Настройте PortFast на всех портах доступа, которые используются на обоих коммутаторах.

![image](https://github.com/user-attachments/assets/4ab86e5f-64f8-4484-a3a8-db7c59a82efb)

![image](https://github.com/user-attachments/assets/4c2f4ae0-3702-475a-a0cc-47e6cfe7109d)

b.	Включите защиту BPDU на портах доступа VLAN 10 S1 и S2, подключенных к PC-A и PC-B.

![image](https://github.com/user-attachments/assets/6baa7683-0da8-4708-94f1-912d2481af62)

![image](https://github.com/user-attachments/assets/13225f35-a4eb-4297-8d92-4ca8c4adedc4)

c.	Убедитесь, что защита BPDU и PortFast включены на соответствующих портах.

![image](https://github.com/user-attachments/assets/be09eda1-422b-4a68-8445-e522a76e56c1)

**Шаг 7. Проверьте наличие сквозного ⁪подключения.**

![image](https://github.com/user-attachments/assets/781630f6-b61a-44da-889b-01b73d04261d)

![image](https://github.com/user-attachments/assets/afcdf942-034a-4cfa-942c-8ff2ca55ca77)











