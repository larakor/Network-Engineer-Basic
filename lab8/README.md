![image](https://github.com/user-attachments/assets/c6e54b66-1d57-4dfd-b0a8-710b36790299)

![image](https://github.com/user-attachments/assets/8497a6bc-bb6b-4098-8405-50ae8379b75f)

**Часть 1.	Создание сети и настройка основных параметров устройства**

**Шаг 1.	Создание схемы адресации**

 a.	Одна подсеть «Подсеть A», поддерживающая 58 хостов (клиентская VLAN на R1).

Подсеть A - Запишите первый IP-адрес в таблице адресации для R1 G0/0/1.100 . 

b.	Одна подсеть «Подсеть B», поддерживающая 28 хостов (управляющая VLAN на R1). 

Подсеть B:Запишите первый IP-адрес в таблице адресации для R1 G0/0/1.200. Запишите второй IP-адрес в таблице адресов для S1 VLAN 200 и введите соответствующий шлюз по умолчанию.

c.	Одна подсеть «Подсеть C», поддерживающая 12 узлов (клиентская сеть на R2).

Подсеть C: Запишите первый IP-адрес в таблице адресации для R2 G0/0/1.

![image](https://github.com/user-attachments/assets/a5ed7680-a457-4f69-b9de-055c96594dbd)


**Шаг 2.	Создайте сеть согласно топологии.**

![image](https://github.com/user-attachments/assets/bb932a5b-15f5-4fca-a756-bfa6db82e35b)

**Шаг 3.	Произведите базовую настройку маршрутизаторов.**

a.	Назначьте маршрутизатору имя устройства.

b.	Отключите поиск DNS, чтобы предотвратить попытки маршрутизатора неверно преобразовывать введенные команды таким образом, как будто они являются именами узлов.

c.	Назначьте class в качестве зашифрованного пароля привилегированного режима EXEC.

d.	Назначьте cisco в качестве пароля консоли и включите вход в систему по паролю.

e.	Назначьте cisco в качестве пароля VTY и включите вход в систему по паролю.

f.	Зашифруйте открытые пароли.

g.	Создайте баннер с предупреждением о запрете несанкционированного доступа к устройству.

h.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.

i.	Установите часы на маршрутизаторе на сегодняшнее время и дату.

![image](https://github.com/user-attachments/assets/a607b1d4-f158-45a2-a5b7-2375d202f3ae)

![image](https://github.com/user-attachments/assets/00cc3fd8-1c3a-4166-90fa-77a32de05630)

![image](https://github.com/user-attachments/assets/c24b776a-4f16-4d44-9a77-b9e0181950f8)

![image](https://github.com/user-attachments/assets/911bc382-970a-4ef3-9e0c-fabe76631748)

![image](https://github.com/user-attachments/assets/11f65dac-28a7-4329-92ff-1841aeaf8b98)

**Шаг 4.	Настройка маршрутизации между сетями VLAN на маршрутизаторе R1**

a.	Активируйте интерфейс G0/0/1 на маршрутизаторе.

![image](https://github.com/user-attachments/assets/eab121a6-6aff-4eed-9a7b-87ca18595614)

b.	Настройте подинтерфейсы для каждой VLAN в соответствии с требованиями таблицы IP-адресации. Все субинтерфейсы используют инкапсуляцию 802.1Q и назначаются первый полезный адрес из вычисленного пула IP-адресов. Убедитесь, что подинтерфейсу для native VLAN не назначен IP-адрес. Включите описание для каждого подинтерфейса.

![image](https://github.com/user-attachments/assets/1f485506-1bd7-4c5f-a061-cddaca1d1ad7)

c.	Убедитесь, что вспомогательные интерфейсы работают.

![image](https://github.com/user-attachments/assets/3df05008-8f24-43be-a541-bf8de2734cac)


**Шаг 5.	Настройте G0/1 на R2, затем G0/0/0 и статическую маршрутизацию для обоих маршрутизаторов**

a.	Настройте G0/0/1 на R2 с первым IP-адресом подсети C, рассчитанным ранее.

![image](https://github.com/user-attachments/assets/1f4dc991-ebd9-4feb-bb97-335b5da6ffcf)

b.	Настройте интерфейс G0/0/0 для каждого маршрутизатора на основе приведенной выше таблицы IP-адресации.

c.	Настройте маршрут по умолчанию на каждом маршрутизаторе, указываемом на IP-адрес G0/0/0 на другом маршрутизаторе.

d.	Убедитесь, что статическая маршрутизация работает с помощью пинга до адреса G0/0/1 R2 от R1.

e.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.

![image](https://github.com/user-attachments/assets/0503cdeb-1709-4884-a301-e4303c08415e)

![image](https://github.com/user-attachments/assets/4985ad55-382d-4ecd-aeba-00c7bb5abe5c)

Пинг проходит от R1 до R2

![image](https://github.com/user-attachments/assets/0702646c-a758-4b8d-bbfa-777c1d4af149)

**Шаг 6.	Настройте базовые параметры каждого коммутатора.**

a.	Присвойте коммутатору имя устройства.

b.	Отключите поиск DNS, чтобы предотвратить попытки маршрутизатора неверно преобразовывать введенные команды таким образом, как будто они являются именами узлов.

c.	Назначьте class в качестве зашифрованного пароля привилегированного режима EXEC.

d.	Назначьте cisco в качестве пароля консоли и включите вход в систему по паролю.

e.	Назначьте cisco в качестве пароля VTY и включите вход в систему по паролю.

f.	Зашифруйте открытые пароли.

g.	Создайте баннер с предупреждением о запрете несанкционированного доступа к устройству.

h.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.

i.	Установите часы на маршрутизаторе на сегодняшнее время и дату.

j.	Скопируйте текущую конфигурацию в файл загрузочной конфигурации.

![image](https://github.com/user-attachments/assets/b9317362-e171-44e0-a576-6611d32b6ab8)

![image](https://github.com/user-attachments/assets/588396b8-9ca2-4f70-91c2-edc274a44366)

**Шаг 7.	Создайте сети VLAN на коммутаторе S1.**

a.	Создайте необходимые VLAN на коммутаторе 1 и присвойте им имена из приведенной выше таблицы.

![image](https://github.com/user-attachments/assets/1994b836-3eef-491d-9e2b-ddd25c68b0ca)

b.	Настройте и активируйте интерфейс управления на S1 (VLAN 200), используя второй IP-адрес из подсети, рассчитанный ранее. Кроме того установите шлюз по умолчанию на S1.

![image](https://github.com/user-attachments/assets/318c9055-2fe9-44e5-b75e-02d10e07851a)

c.	Настройте и активируйте интерфейс управления на S2 (VLAN 1), используя второй IP-адрес из подсети, рассчитанный ранее. Кроме того, установите шлюз по умолчанию на S2

![image](https://github.com/user-attachments/assets/2979332b-3cf8-4676-a8cf-acfc71e406ad)

d.	Назначьте все неиспользуемые порты S1 VLAN Parking_Lot, настройте их для статического режима доступа и административно деактивируйте их. На S2 административно деактивируйте все неиспользуемые порты.

![image](https://github.com/user-attachments/assets/9e5ec768-3d04-49bb-ac3d-f3bdbfb7aefb)

![image](https://github.com/user-attachments/assets/57c91a88-c1e0-441b-b89d-f9a8c9ab859d)

**Шаг 8.	Назначьте сети VLAN соответствующим интерфейсам коммутатора.**

a.	Назначьте используемые порты соответствующей VLAN (указанной в таблице VLAN выше) и настройте их для режима статического доступа.

![image](https://github.com/user-attachments/assets/2e53b791-d9e5-4e1e-8425-50d678b316b3)

![image](https://github.com/user-attachments/assets/6191835a-2264-4fbc-a14f-8fec46c8b93d)

b.	Убедитесь, что VLAN назначены на правильные интерфейсы.

![image](https://github.com/user-attachments/assets/f9d78589-4cec-4afc-a9f8-3e2ee81b01fc)


**Шаг 9.	Вручную настройте интерфейс S1 F0/5 в качестве транка 802.1Q.**

a.	Измените режим порта коммутатора, чтобы принудительно создать магистральный канал.

b.	В рамках конфигурации транка  установите для native  VLAN значение 1000.

c.	В качестве другой части конфигурации магистрали укажите, что VLAN 100, 200 и 1000 могут проходить по транку.

d.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.

e.	Проверьте состояние транка.

![image](https://github.com/user-attachments/assets/47e42800-18a3-42d9-9d9f-795b27a13f49)

![image](https://github.com/user-attachments/assets/51ac5cc4-5505-4b25-bda2-d77a897001b4)

![image](https://github.com/user-attachments/assets/bc785a16-b580-4dfb-ba2d-1457d1edd6e2)

![image](https://github.com/user-attachments/assets/a0cbec95-c832-4e2a-b1b5-1c8800c40507)

**Часть 2.	Настройка и проверка двух серверов DHCPv4 на R1**

**Шаг 1.	Настройте R1 с пулами DHCPv4 для двух поддерживаемых подсетей. Ниже приведен только пул DHCP для подсети A**

a.	Исключите первые пять используемых адресов из каждого пула адресов.

b.	Создайте пул DHCP (используйте уникальное имя для каждого пула).

c.	Укажите сеть, поддерживающую этот DHCP-сервер.

d.	В качестве имени домена укажите CCNA-lab.com.

e.	Настройте соответствующий шлюз по умолчанию для каждого пула DHCP.

f.	Настройте время аренды на 2 дня 12 часов и 30 минут.

![image](https://github.com/user-attachments/assets/7712a3a1-83bf-4ae2-bbd4-1cb4f2d204db)

![image](https://github.com/user-attachments/assets/743edf90-8272-4e52-ab90-da1682750b30)

![image](https://github.com/user-attachments/assets/7eef7ac0-2096-4b91-b337-e4133d6172ae)

![image](https://github.com/user-attachments/assets/deb3841d-4e12-4aa3-af05-e6290b208af3)

g.	Затем настройте второй пул DHCPv4, используя имя пула R2_Client_LAN и вычислите сеть, маршрутизатор по умолчанию, и используйте то же имя домена и время аренды, что и предыдущий пул DHCP.

![image](https://github.com/user-attachments/assets/07e889c5-3c26-45fa-8312-c3c29e7c4583)

![image](https://github.com/user-attachments/assets/c44c71d0-d69c-49eb-934f-ae44bb91a178)

**Шаг 2.	Сохраните конфигурацию.**

Сохраните текущую конфигурацию в файл загрузочной конфигурации.

![image](https://github.com/user-attachments/assets/f5745e3d-307d-4225-9f52-4f5115f6532b)


**Шаг 3.	Проверка конфигурации сервера DHCPv4**

a.	Чтобы просмотреть сведения о пуле, выполните команду show ip dhcp pool .

![image](https://github.com/user-attachments/assets/6f12e720-092d-40dd-812c-ac6802e1e340)

b.	Выполните команду show ip dhcp bindings для проверки установленных назначений адресов DHCP.

![image](https://github.com/user-attachments/assets/9b689980-e57f-469d-bdb1-ddcb012875aa)

**Шаг 4.	Попытка получить IP-адрес от DHCP на PC-A**

![image](https://github.com/user-attachments/assets/9bac4d4d-6692-428f-9167-df998398a387)

a.	Из командной строки компьютера PC-A выполните команду ipconfig /all.

![image](https://github.com/user-attachments/assets/a8fd55ef-f2cd-4ad4-9fe2-57b3713512d8)

![image](https://github.com/user-attachments/assets/d7c3c559-0f96-4416-aeeb-36866e52e3fa)

**Часть 3.	Настройка и проверка DHCP-ретрансляции на R2**

**Шаг 1.	Настройка R2 в качестве агента DHCP-ретрансляции для локальной сети на G0/0/1**

a.	Настройте команду ip helper-address на G0/0/1, указав IP-адрес G0/0/0 R1.

Почему-то это не работает, поэтому просто настроим R2 как DHCP сервер

![image](https://github.com/user-attachments/assets/b3b3424f-ad6f-4b67-8e2c-66074cdaf4e5)

b.	Сохраните конфигурацию.

**Шаг 2.	Попытка получить IP-адрес от DHCP на PC-B**

a.	Из командной строки компьютера PC-B выполните команду ipconfig /all.

b.	После завершения процесса обновления выполните команду ipconfig для просмотра новой информации об IP-адресе.

c.	Проверьте подключение с помощью пинга IP-адреса интерфейса R1 G0/0/1.

d.	Выполните show ip dhcp binding для R1 для проверки назначений адресов в DHCP.

![image](https://github.com/user-attachments/assets/d81c9ded-e458-45ae-9992-5bc4b0abe86b)

![image](https://github.com/user-attachments/assets/8df6cb10-b056-4b52-855d-bc601007b74b)

![image](https://github.com/user-attachments/assets/61b1f63c-def8-4a4a-ac5d-62f47a75e6bc)








