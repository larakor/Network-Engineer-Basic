![image](https://github.com/user-attachments/assets/72be1e13-1dc1-4f4d-b10a-6dbe60a9aaa4)


**ВЫПОЛНЕНИЕ**

![image](https://github.com/user-attachments/assets/58b6bb5e-8d9a-4e38-a0e7-97d71641323e)


**Часть 1. Настройка топологии и конфигурация основных параметров маршрутизатора и коммутатора**

**Шаг 1. Настройка маршрутизатора**

![image](https://github.com/user-attachments/assets/171fdcad-8db1-426f-a5f1-14f4ce027870)


**Шаг 2. Настройка коммутатора**

![image](https://github.com/user-attachments/assets/5ec67528-df98-4f78-8a42-0c55e14c38e3)


**Часть 2. Ручная настройка IPv6-адресов**

**Шаг 1. Назначьте IPv6-адреса интерфейсам Ethernet на R1.**

a.	Назначьте глобальные индивидуальные IPv6-адреса, указанные в таблице адресации обоим интерфейсам Ethernet на R1.

![image](https://github.com/user-attachments/assets/615fb146-b8dc-410d-aefb-3fb5d185fd7e)


b.	Введите команду show ipv6 interface brief, чтобы проверить, назначен ли каждому интерфейсу корректный индивидуальный IPv6-адрес.

![image](https://github.com/user-attachments/assets/86a75773-6050-410c-9070-fbcffe8b0908)


c.	Чтобы обеспечить соответствие локальных адресов канала индивидуальному адресу, вручную введите локальные адреса канала на каждом интерфейсе Ethernet на R1.

![image](https://github.com/user-attachments/assets/fc0b354b-f0d0-49ff-b244-ccd15a3eda23)


d.	Используйте выбранную команду, чтобы убедиться, что локальный адрес связи изменен на fe80::1.  

![image](https://github.com/user-attachments/assets/4b6437b3-8bae-4064-931a-555ace11ad9f)


**Шаг 2. Активируйте IPv6-маршрутизацию на R1.**

**a.	В командной строке на PC-B введите команду ipconfig, чтобы получить данные IPv6-адреса, назначенного интерфейсу ПК.**

![image](https://github.com/user-attachments/assets/b7458881-9bca-48b1-93e8-4d4341abc3cb)

Вопрос:
Назначен ли индивидуальный IPv6-адрес сетевой интерфейсной карте (NIC) на PC-B? - НЕТ

**b.	Активируйте IPv6-маршрутизацию на R1 с помощью команды IPv6 unicast-routing.**

![image](https://github.com/user-attachments/assets/f5223eb4-071f-4ef1-b8db-f27bf98f7ddd)

**c.	Теперь, когда R1 входит в группу многоадресной рассылки всех маршрутизаторов, еще раз введите команду ipconfig на PC-B. Проверьте данные IPv6-адреса.**

![image](https://github.com/user-attachments/assets/ab9fbaf1-a086-4748-b68d-405f21998b6b)

**Шаг 3. Назначьте IPv6-адреса интерфейсу управления (SVI) на S1.**

**a.	Назначьте адрес IPv6 для S1. Также назначьте этому интерфейсу локальный адрес канала fe80::b.**

![image](https://github.com/user-attachments/assets/de780037-5a9c-4792-8492-7eebd5053b0a)

**b.	Проверьте правильность назначения IPv6-адресов интерфейсу управления с помощью команды show ipv6 interface vlan1.**

![image](https://github.com/user-attachments/assets/f6990d07-ce64-4611-88f1-1d00bbafd8ee)


**Шаг 4. Назначьте компьютерам статические IPv6-адреса.**

**a.	Откройте окно Свойства Ethernet для каждого ПК и назначьте адресацию IPv6.**

![image](https://github.com/user-attachments/assets/f5e8c239-d8a2-4ed0-a92d-58e3cd14e7fa)

![image](https://github.com/user-attachments/assets/dba0e66a-5e38-4028-8e04-07b2f4a297b0)

**b.	Убедитесь, что оба компьютера имеют правильную информацию адреса IPv6. Каждый компьютер должен иметь два глобальных адреса IPv6: один статический и один SLACC.**

![image](https://github.com/user-attachments/assets/1692dc3e-e003-4f7d-b510-1846b9620836)

![image](https://github.com/user-attachments/assets/1013db5a-637d-4df7-b4e7-83383b4e80d8)

**Часть 3. Проверка сквозного подключения**

С PC-A отправьте эхо-запрос на FE80::1. Это локальный адрес канала, назначенный G0/1 на R1.

![image](https://github.com/user-attachments/assets/1c656b9d-3666-424d-af64-c8bc4b7a37ae)

Отправьте эхо-запрос на интерфейс управления S1 с PC-A.

![image](https://github.com/user-attachments/assets/071265e8-3af0-42e4-8369-06b09d89f11c)

Введите команду tracert на PC-A, чтобы проверить наличие сквозного подключения к PC-B.

![image](https://github.com/user-attachments/assets/3abf4593-603f-4254-b484-748977878fd2)

С PC-B отправьте эхо-запрос на PC-A.

![image](https://github.com/user-attachments/assets/b9a99a25-fa45-4baa-8e54-072797a04d50)


С PC-B отправьте эхо-запрос на локальный адрес канала G0/0 на R1.

![image](https://github.com/user-attachments/assets/3a51b2bc-9c08-4f87-ae69-f8596747bd19)





