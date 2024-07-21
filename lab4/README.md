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



Вопрос:
Почему PC-B получил глобальный префикс маршрутизации и идентификатор подсети, которые вы настроили на R1?






