![image](https://github.com/user-attachments/assets/0ba072f6-7680-42c6-b036-7f5cf6389934)

** ВЫПОЛНЕНИЕ **

**Часть 1:	Создание сети и настройка основных параметров устройства**

**Шаг 1:	Создайте сеть согласно топологии.**

![image](https://github.com/user-attachments/assets/f1a405fa-4624-4187-86b0-b94066800808)

**Шаг 2:	Выполните инициализацию и перезагрузку коммутаторов.**

Выполнили на всех трех коммутаторах:

![image](https://github.com/user-attachments/assets/f7f9b776-8eb8-479e-b068-7b68f6e460f5)

**Шаг 3:	Настройте базовые параметры каждого коммутатора.**

a.	Отключите поиск DNS.

b.	Присвойте имена устройствам в соответствии с топологией.

c.	Назначьте class в качестве зашифрованного пароля доступа к привилегированному режиму.

d.	Назначьте cisco в качестве паролей консоли и VTY и активируйте вход для консоли и VTY каналов.

e.	Настройте logging synchronous для консольного канала.

f.	Настройте баннерное сообщение дня (MOTD) для предупреждения пользователей о запрете несанкционированного доступа.

g.	Задайте IP-адрес, указанный в таблице адресации для VLAN 1 на всех коммутаторах.

h.	Скопируйте текущую конфигурацию в файл загрузочной конфигурации.

![image](https://github.com/user-attachments/assets/084cf199-8023-4f66-b411-eceabcefde6f)

![image](https://github.com/user-attachments/assets/d3445c2d-4380-44bd-bdda-9609e24e30e4)

![image](https://github.com/user-attachments/assets/d29bc5ba-d921-4f30-a8c5-6235baf0dd43)

**Шаг 4:	Проверьте связь.**

Проверьте способность компьютеров обмениваться эхо-запросами.

![image](https://github.com/user-attachments/assets/1c93883a-625d-452a-9a98-a29c65f316b0)

![image](https://github.com/user-attachments/assets/102dd111-a87e-4eaf-b63d-98fa8e810187)

**Часть 2:	Определение корневого моста**

**Шаг 1:	Отключите все порты на коммутаторах.**

на всех коммутаторах сделали:

![image](https://github.com/user-attachments/assets/6d30b1b3-8268-4a89-8b72-fefe4faf16e9)

**Шаг 2:	Настройте подключенные порты в качестве транковых.**

на всех коммутаторах ввели:

![image](https://github.com/user-attachments/assets/ee478f29-6559-4228-ba7a-cc4c1f35da66)

**Шаг 3:	Включите порты F0/2 и F0/4 на всех коммутаторах.**

на всех коммутаторах выполнили:

![image](https://github.com/user-attachments/assets/d1b64568-6b8d-49d0-83af-905aaaba959a)

**Шаг 4:	Отобразите данные протокола spanning-tree.**

![image](https://github.com/user-attachments/assets/e0ba46a2-624a-4cf8-8da1-91b8775ebbab)

![image](https://github.com/user-attachments/assets/71cb0327-1222-4407-81e8-9554924b1893)

![image](https://github.com/user-attachments/assets/c170df29-b686-429b-b905-fdac357359e8)

**Какой коммутатор является корневым мостом?* - S2

**Почему этот коммутатор был выбран протоколом spanning-tree в качестве корневого моста?*

S2 имеет наименьший Bridge ID - Bridge ID  Priority    32769  (priority 32768 sys-id-ext 1)
                                Address     0003.E425.6399

**Какие порты на коммутаторе являются корневыми портами?* 

На S1 корневой порт F0/4 , на  S3 корневой порт F0/4 

**Какие порты на коммутаторе являются назначенными портами?* S2 - f0/2, f0/4 и S3 f0/2

**Какой порт отображается в качестве альтернативного и в настоящее время заблокирован?* S1 порт f0/2

**Почему протокол spanning-tree выбрал этот порт в качестве невыделенного (заблокированного) порта?*

Данный алгоритм выбирает пути, отталкиваясь от корневого моста и определяет альтернативный порт исходя из стоимости, если стоимости одинаковые, то сравнивается BID. Блокируется порт с наивысшим BID.

**Часть 3:	Наблюдение за процессом выбора протоколом STP порта, исходя из стоимости портов**

**Шаг 1:	Определите коммутатор с заблокированным портом.**

![image](https://github.com/user-attachments/assets/d131775e-08c3-4449-9bbf-9dc49ba68729)

![image](https://github.com/user-attachments/assets/7402783b-8fb1-4a03-888f-adfb7e636820)

В данном случае протокол spanning-tree блокирует порт F0/2 на коммутаторе S1 (самым высокий идентификатор BID).

**Шаг 2:	Измените стоимость порта.**

Уменьшаем стоимость порта корневого моста до 18, выполнив команду spanning-tree vlan 1 cost 18 режима конфигурации интерфейса.

![image](https://github.com/user-attachments/assets/4cdeb6de-5143-403e-83b6-3efaf25feb6c)

**Шаг 3:	Просмотрите изменения протокола spanning-tree.**

![image](https://github.com/user-attachments/assets/efe80d10-e12e-4298-94d0-cf3616bbd1dd)

![image](https://github.com/user-attachments/assets/dfa6f972-b28b-4d7a-adfd-f097781c6019)

И теперь заблокированным стал порт на коммутаторе S3 - f0/2. Опять же по принципу наивысшей стоимости порта.

**Шаг 4:	Удалите изменения стоимости порта.**

**a.	Выполните команду no spanning-tree vlan 1 cost 18 режима конфигурации интерфейса, чтобы удалить запись стоимости, созданную ранее.**

![image](https://github.com/user-attachments/assets/549f5b69-f962-4e67-ac9b-0b82f2798ca2)

**b.	Повторно выполните команду show spanning-tree**

![image](https://github.com/user-attachments/assets/5db884e5-1c4f-428b-812b-49354e825411)

![image](https://github.com/user-attachments/assets/7d0b10bf-e734-4900-ab75-cdd5d752cb9b)

Порты снова вернулись в первоначальное состояние.

**Часть 4:	Наблюдение за процессом выбора протоколом STP порта, исходя из приоритета портов**

**a.	Включите порты F0/1 и F0/3 на всех коммутаторах.**

![image](https://github.com/user-attachments/assets/465f63c5-c908-463e-9a89-599bdb0c775d)

![image](https://github.com/user-attachments/assets/e4fcd9de-7646-4a1c-886c-92db8bb5a4c7)

![image](https://github.com/user-attachments/assets/83f08594-aa98-447f-aa64-a2e3c01c646a)

**b.	Выполните команду show spanning-tree на коммутаторах некорневого моста.** 

![image](https://github.com/user-attachments/assets/15c44f63-1c77-4967-bd00-4aa6c65a89bf)

![image](https://github.com/user-attachments/assets/c6ada6d2-e314-4479-aeaf-59fd585418bd)

Теперь порт корневого моста переместился на порт с меньшим номером - f0/3, заблокировал предыдущий порт корневого моста - f0/4.

![image](https://github.com/user-attachments/assets/ce15ae2d-df0f-43c5-9959-f39882a3ede6)

Во всех случаях выбирается наименьшее значение




