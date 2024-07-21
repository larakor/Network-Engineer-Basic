![image](https://github.com/user-attachments/assets/72be1e13-1dc1-4f4d-b10a-6dbe60a9aaa4)


**ВЫПОЛНЕНИЕ**

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









