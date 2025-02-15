![image](https://github.com/user-attachments/assets/ff9b4352-fb2b-41a3-91f6-eb0c0bda48d9)

![image](https://github.com/user-attachments/assets/1adb3e83-6ff3-4863-bb48-36f94a76db77)

![image](https://github.com/user-attachments/assets/f8628da1-308e-40d4-9549-58eba52e42fb)

**ВЫПОЛНЕНИЕ**

**Часть 1. Создание сети и настройка основных параметров устройства**

Шаг 1. Создайте сеть согласно топологии. Подключите устройства, как показано в топологии, и подсоедините необходимые кабели.

![image](https://github.com/user-attachments/assets/a0cf6f0c-5417-4720-a2ce-9be07ec0e0a8)

**Шаг 2. Произведите базовую настройку маршрутизаторов.**

a.	Назначьте маршрутизатору имя устройства.

b.	Отключите поиск DNS, чтобы предотвратить попытки маршрутизатора неверно преобразовывать введенные команды таким образом, как будто они являются именами узлов.

c.	Назначьте class в качестве зашифрованного пароля привилегированного режима EXEC.

d.	Назначьте cisco в качестве пароля консоли и включите вход в систему по паролю.

e.	Назначьте cisco в качестве пароля VTY и включите вход в систему по паролю.

f.	Зашифруйте открытые пароли.

g.	Создайте баннер с предупреждением о запрете несанкционированного доступа к устройству.

h.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.

![image](https://github.com/user-attachments/assets/f2fd4658-709f-4414-9acb-3f37c44e9fc7)

![image](https://github.com/user-attachments/assets/d10eef30-187a-472e-b874-566bc7c4b1a1)

**Шаг 3. Настройте базовые параметры каждого коммутатора.**

a.	Присвойте коммутатору имя устройства.

b.	Отключите поиск DNS, чтобы предотвратить попытки маршрутизатора неверно преобразовывать введенные команды таким образом, как будто они являются именами узлов.

c.	Назначьте class в качестве зашифрованного пароля привилегированного режима EXEC.

d.	Назначьте cisco в качестве пароля консоли и включите вход в систему по паролю.

e.	Назначьте cisco в качестве пароля VTY и включите вход в систему по паролю.

f.	Зашифруйте открытые пароли.

g.	Создайте баннер с предупреждением о запрете несанкционированного доступа к устройству.

h.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.

![image](https://github.com/user-attachments/assets/fd0abab6-c98f-4b9e-86a7-31b55c26d9b3)

![image](https://github.com/user-attachments/assets/ae046b10-e587-4f9b-aad8-6671b4e19d64)

**Часть 2. Настройка сетей VLAN на коммутаторах.**

**Шаг 1. Создайте сети VLAN на коммутаторах.**

a.	Создайте необходимые VLAN и назовите их на каждом коммутаторе из приведенной выше таблицы.

![image](https://github.com/user-attachments/assets/d6f6207f-d350-4c7c-aac8-04c37f716512)

![image](https://github.com/user-attachments/assets/7e65a745-3023-4f0f-a26d-afb3399d0e30)

b.	Настройте интерфейс управления и шлюз по умолчанию на каждом коммутаторе, используя информацию об IP-адресе в таблице адресации. 

c.	Назначьте все неиспользуемые порты коммутатора VLAN Parking Lot, настройте их для статического режима доступа и административно деактивируйте их.

![image](https://github.com/user-attachments/assets/592f1412-c549-4add-ab1c-ad46244081a9)

![image](https://github.com/user-attachments/assets/9767bb6b-0109-40d7-a30d-b2fe695022e7)

**Шаг 2. Назначьте сети VLAN соответствующим интерфейсам коммутатора.**

a.	Назначьте используемые порты соответствующей VLAN (указанной в таблице VLAN выше) и настройте их для режима статического доступа.

![image](https://github.com/user-attachments/assets/5cfa1bef-6b5f-4c76-818f-be4e07d99a7e)

![image](https://github.com/user-attachments/assets/1fe9b83b-96aa-4a32-bee2-6a7eee3f646f)

b.	Выполните команду show vlan brief, чтобы убедиться, что сети VLAN назначены правильным интерфейсам.

![image](https://github.com/user-attachments/assets/c270bed3-8565-442c-8c7f-d0f64204eb11)

![image](https://github.com/user-attachments/assets/811f0efa-5416-480a-b56b-71b6683b2940)

**Часть 3. Настройте транки (магистральные каналы).**

**Шаг 1. Вручную настройте магистральный интерфейс F0/1.**

a.	Измените режим порта коммутатора на интерфейсе F0/1, чтобы принудительно создать магистральную связь. Не забудьте сделать это на обоих коммутаторах.

b.	В рамках конфигурации транка установите для native vlan значение 1000 на обоих коммутаторах. При настройке двух интерфейсов для разных собственных VLAN сообщения об ошибках могут отображаться временно.

c.	В качестве другой части конфигурации транка укажите, что VLAN 10, 20, 30 и 1000 разрешены в транке.

![image](https://github.com/user-attachments/assets/ad63f604-9ae0-49ba-aa83-516b2b1d5186)

![image](https://github.com/user-attachments/assets/ba61b4b3-59e8-43c5-b1dc-82e63aa140e0)

d.	Выполните команду show interfaces trunk для проверки портов магистрали, собственной VLAN и разрешенных VLAN через магистраль.

![image](https://github.com/user-attachments/assets/1acddeaa-3200-4242-b6ee-10022d04acb9)

![image](https://github.com/user-attachments/assets/0b8af357-ac61-4de7-bcb9-cc7ea56b3ba2)

**Шаг 2. Вручную настройте магистральный интерфейс F0/5 на коммутаторе S1.**

a.	Настройте интерфейс S1 F0/5 с теми же параметрами транка, что и F0/1. Это транк до маршрутизатора.

b.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.

![image](https://github.com/user-attachments/assets/56c787fe-451a-4caa-ad52-6e8b94b387e4)

c.	Используйте команду show interfaces trunk для проверки настроек транка. (перед этим разблокировав порт на R1)

![image](https://github.com/user-attachments/assets/6e386198-cbaa-410d-a088-d7fe0192670d)

**Часть 4. Настройте маршрутизацию.**

**Шаг 1. Настройка маршрутизации между сетями VLAN на R1.**

a.	Активируйте интерфейс G0/0/1 на маршрутизаторе.

![image](https://github.com/user-attachments/assets/c3bf8425-d0c0-413e-8009-e7e669c44a6c)

b.	Настройте подинтерфейсы для каждой VLAN, как указано в таблице IP-адресации. Все подинтерфейсы используют инкапсуляцию 802.1Q. Убедитесь, что подинтерфейс для собственной VLAN не имеет назначенного IP-адреса. Включите описание для каждого подинтерфейса.

![image](https://github.com/user-attachments/assets/6618a351-29c2-4394-b954-e04fbe9732e8)

![image](https://github.com/user-attachments/assets/e0e23aef-9843-4d70-a531-aaa7c4c5ef38)

c.	Настройте интерфейс Loopback 1 на R1 с адресацией из приведенной выше таблицы.

![image](https://github.com/user-attachments/assets/62ef3667-d0a2-47e2-8e06-c6f030ddc7ba)

d.	С помощью команды show ip interface brief проверьте конфигурацию подынтерфейса.

![image](https://github.com/user-attachments/assets/1fe6fc0a-b7f6-49ad-b228-5314ab3d0ee2)

**Шаг 2. Настройка интерфейса R2 g0/0/1 с использованием адреса из таблицы и маршрута по умолчанию с адресом следующего перехода 10.20.0.1**

![image](https://github.com/user-attachments/assets/37eec6c1-ef60-4c84-a7be-70afc62a1c88)

![image](https://github.com/user-attachments/assets/b90b0c22-a7a5-4d0e-a0ef-4efe6b9f8000)

**Часть 5. Настройте удаленный доступ**

**Шаг 1. Настройте все сетевые устройства для базовой поддержки SSH.**

a.	Создайте локального пользователя с именем пользователя SSHadmin и зашифрованным паролем $cisco123!

b.	Используйте ccna-lab.com в качестве доменного имени.

c.	Генерируйте криптоключи с помощью 1024 битного модуля.

d.	Настройте первые пять линий VTY на каждом устройстве, чтобы поддерживать только SSH-соединения и с локальной аутентификацией.

![image](https://github.com/user-attachments/assets/1eec8f50-1eb1-470d-8655-bacf086132b3)

**Шаг 2. Включите защищенные веб-службы с проверкой подлинности на R1.**

a.	Включите сервер HTTPS на R1.       *R1(config)# ip http secure-server*

b.	Настройте R1 для проверки подлинности пользователей, пытающихся подключиться к веб-серверу.   *R1(config)# ip http authentication local*

![image](https://github.com/user-attachments/assets/c40bae91-a5e9-4c67-a797-caf681022d6b)

**Часть 6. Проверка подключения**

**Шаг 1. Настройте узлы ПК.**

![image](https://github.com/user-attachments/assets/3b405070-39ce-4826-b0ae-320ba59a3986)

![image](https://github.com/user-attachments/assets/e71f6ef9-dbd8-41e0-8fe8-6e8891772dd7)

**Шаг 2. Выполните следующие тесты. Эхозапрос должен пройти успешно.**

![image](https://github.com/user-attachments/assets/550f83e9-146c-49fc-8eb5-eeba94c2683c)

![image](https://github.com/user-attachments/assets/15f2cddc-b30f-4681-b0ae-de90d1955c6c)

![image](https://github.com/user-attachments/assets/e96dac43-f7a1-4298-ab21-35c1efcad9f6)

![image](https://github.com/user-attachments/assets/ec30e63a-41cd-408d-a387-57050e0f23de)

![image](https://github.com/user-attachments/assets/7a099140-3a43-4ad0-b581-6afed45e39bb)

![image](https://github.com/user-attachments/assets/c6d12d2e-cce3-49b4-bd58-fe7f09065dbf)

**Часть 7. Настройка и проверка списков контроля доступа (ACL)**

При проверке базового подключения компания требует реализации следующих политик безопасности:

Политика1. Сеть Sales не может использовать SSH в сети Management (но в  другие сети SSH разрешен). 

Политика 2. Сеть Sales не имеет доступа к IP-адресам в сети Management с помощью любого веб-протокола (HTTP/HTTPS). Сеть Sales также не имеет доступа к интерфейсам R1 с помощью любого веб-протокола. Разрешён весь другой веб-трафик (обратите внимание — Сеть Sales  может получить доступ к интерфейсу Loopback 1 на R1).

Политика3. Сеть Sales не может отправлять эхо-запросы ICMP в сети Operations или Management. Разрешены эхо-запросы ICMP к другим адресатам. 

Политика 4: Cеть Operations  не может отправлять ICMP эхозапросы в сеть Sales. Разрешены эхо-запросы ICMP к другим адресатам. 

**Шаг 1. Проанализируйте требования к сети и политике безопасности для планирования реализации ACL.**

- поскольку в условиях испозьзуются: адрес источника и адрес назначенияб и предмет запретаб и порт - значит будем использовать расширенный список  - extended

- в первых трех пунктах все запреты (deny) касаются сети Sales, можно их объединить их в один лист и прикрепить этот список конкретно на этот подынтерфейс. Поскольку, как я понимаю, на один порт возможно прикрпеить только один ACL (??или нет??). Порт g0/0/1.40

- соответсвенно Operations прикрепим к подпорту g0/0/1.30

**Шаг 2. Разработка и применение расширенных списков доступа, которые будут соответствовать требованиям политики безопасности.**

сначала создаем список и именуем его

![image](https://github.com/user-attachments/assets/9865474a-8454-4aa6-9f9b-cdba94f94f7b)

Далее идём попунктно:

1. добавим строку запрета доступа по SSH только в сети Management: параметор протокола - tcp, адрес источника - полностью сеть Sale, адрес назначения - полностью сеть Management, для SSH укажем порт 22

   ![image](https://github.com/user-attachments/assets/69cd6fdd-2815-4b36-95eb-7a1e34b26d54)

2. *Сеть Sales не имеет доступа к IP-адресам в сети Management с помощью любого веб-протокола (HTTP/HTTPS)* - то же самое, но выберем порты HTTP/HTTPS 80 и 443

   ![image](https://github.com/user-attachments/assets/fa74cec6-c163-4021-a53c-b11ea00176ea)

*Сеть Sales также не имеет доступа к интерфейсам R1 с помощью любого веб-протокола.* - также берем порты 80 и 443, адресами назначения возьмем подынтерфейсы (весь интерфейс не берем, т.к. совсем тогда не достучимся)

![image](https://github.com/user-attachments/assets/0db5a76f-933b-4fb1-8a6e-0c3f5f41c606)

3. *Сеть Sales не может отправлять эхо-запросы ICMP в сети Operations или Management. Разрешены эхо-запросы ICMP к другим адресатам.* - адресатами берем полностью сети Management (20) и Operations (30), берем параметр echo

![image](https://github.com/user-attachments/assets/9f1ce9f1-384e-46b8-a878-34f67c720af9)

Поставили все запреты, остальное должно быть разрешено

![image](https://github.com/user-attachments/assets/1b0fd5a2-8be5-4b8f-9fab-f7094ba02ef7)

Проверим готовый ACL

![image](https://github.com/user-attachments/assets/d16477df-aa89-4ae2-a6e6-115f23725c00)

Далее прикрепим его на нужный нам подынтерфейс

![image](https://github.com/user-attachments/assets/df9ef00e-e391-4589-8f0e-def6407c8d0e)

4. *Cеть Operations  не может отправлять ICMP эхозапросы в сеть Sales. Разрешены эхо-запросы ICMP к другим адресатам.* - создаем отдельный ACL (таким же образом, тут будет одно запрещающее правило, остальное разрешим) и крепим к соответсвующему интерефейсу

![image](https://github.com/user-attachments/assets/59a68f28-795b-48e1-9cc7-cae78bfe2901)

**Шаг 3. Убедитесь, что политики безопасности применяются развернутыми списками доступа.**

![image](https://github.com/user-attachments/assets/735c05ad-02af-4497-bf37-9460853aac7d)

![image](https://github.com/user-attachments/assets/15adcf9f-8ac5-4ca9-93c7-280fe5eb4202)

![image](https://github.com/user-attachments/assets/1f22cb1a-5e99-44d1-81f2-02b89f345594)

![image](https://github.com/user-attachments/assets/34a57d9b-0ca6-4bf9-a6ff-bc04b0e8d833)

![image](https://github.com/user-attachments/assets/57cbe8f7-dd1d-4522-a20f-ee62b0c43006)

![image](https://github.com/user-attachments/assets/fb03a920-61bf-457c-a697-f00acc42197f)

![image](https://github.com/user-attachments/assets/f07249bb-5e81-403c-870b-a77d16329c30)

![image](https://github.com/user-attachments/assets/18da6438-ef38-4857-9176-2eed467034b8)






