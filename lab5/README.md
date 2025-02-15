![image](https://github.com/user-attachments/assets/ad14b4d1-ed9d-4469-8662-5685a73c45ff)


**ВЫПОЛНЕНИЕ**

**Часть 1. Настройка основных параметров устройств**

**Шаг 1. Создайте сеть согласно топологии.**

![image](https://github.com/user-attachments/assets/73467b0f-ab7c-4800-a469-50261f657d0d)


**Шаг 2. Выполните инициализацию и перезагрузку маршрутизатора и коммутатора.**

Коммутатор

![image](https://github.com/user-attachments/assets/657ad365-3263-4e80-8c4d-0b0e46908a5e)

Маршрутизатор

![image](https://github.com/user-attachments/assets/7b3f262c-392a-40df-8565-38415807bff0)

**Шаг 3. Настройте маршрутизатор.**

a.	Подключитесь к маршрутизатору с помощью консоли и активируйте привилегированный режим EXEC.

b.	Войдите в режим конфигурации.

c.	Отключите поиск DNS, чтобы предотвратить попытки маршрутизатора неверно преобразовывать введенные команды таким образом, как будто они являются именами узлов.

d.	Назначьте class в качестве зашифрованного пароля привилегированного режима EXEC.

e.	Назначьте cisco в качестве пароля консоли и включите вход в систему по паролю.

f.	Назначьте cisco в качестве пароля VTY и включите вход в систему по паролю.

g.	Зашифруйте открытые пароли.

h.	Создайте баннер, который предупреждает о запрете несанкционированного доступа.

i.	Настройте и активируйте на маршрутизаторе интерфейс G0/0/1, используя информацию, приведенную в таблице адресации.

j.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.

![image](https://github.com/user-attachments/assets/e30bde85-fe78-4e9b-a6c3-3b83e62d879e)

**Шаг 4. Настройте компьютер PC-A.**

**a.	Настройте для PC-A IP-адрес и маску подсети.**

**b.	Настройте для PC-A шлюз по умолчанию.**

![image](https://github.com/user-attachments/assets/b8878aca-00ef-4815-a2c4-f0529d858dbf)


**Шаг 5. Проверьте подключение к сети.**

Пошлите с PC-A команду Ping на маршрутизатор R1. 

![image](https://github.com/user-attachments/assets/811c5daf-f3b1-4690-a598-8690b6ce0f08)

**Часть 2. Настройка маршрутизатора для доступа по протоколу SSH**

**Шаг 1. Настройте аутентификацию устройств.**

Откройте окно конфигурации

a.	Задайте имя устройства.

b.	Задайте домен для устройства.

![image](https://github.com/user-attachments/assets/29dc8eda-1884-4173-b440-2d6167172656)


**Шаг 2. Создайте ключ шифрования с указанием его длины.**

![image](https://github.com/user-attachments/assets/85db9c4e-7446-4e75-b6d7-243742e0493b)

**Шаг 3. Создайте имя пользователя в локальной базе учетных записей.**

Настройте имя пользователя, используя admin в качестве имени пользователя и Adm1nP@55 в качестве пароля.

![image](https://github.com/user-attachments/assets/8bbaaf77-44d6-4136-b862-d2545d35419c)

**Шаг 4. Активируйте протокол SSH на линиях VTY.**

a.	Активируйте протоколы Telnet и SSH на входящих линиях VTY с помощью команды transport input.(см ниже)

b.	Измените способ входа в систему таким образом, чтобы использовалась проверка пользователей по локальной базе учетных записей.(см ниже)

**Шаг 5. Сохраните текущую конфигурацию в файл загрузочной конфигурации.**

![image](https://github.com/user-attachments/assets/e4a9577e-0845-47e9-812d-48d4f484932c)

**Шаг 6. Установите соединение с маршрутизатором по протоколу SSH.**

a.	Запустите Tera Term с PC-A.

b.	Установите SSH-подключение к R1. Use the username admin and password Adm1nP@55. У вас должно получиться установить SSH-подключение к R1.

![image](https://github.com/user-attachments/assets/e2d3dea5-3888-4255-bd82-490bbb08343d)


![image](https://github.com/user-attachments/assets/3db60e6b-a1eb-4d27-953d-1548f911bc04)


**Часть 3. Настройка коммутатора для доступа по протоколу SSH**

**Шаг 1. Настройте основные параметры коммутатора.**

a.	Подключитесь к коммутатору с помощью консольного подключения и активируйте привилегированный режим EXEC.

b.	Войдите в режим конфигурации.

c.	Отключите поиск DNS, чтобы предотвратить попытки маршрутизатора неверно преобразовывать введенные команды таким образом, как будто они являются именами узлов.

d.	Назначьте class в качестве зашифрованного пароля привилегированного режима EXEC.

e.	Назначьте cisco в качестве пароля консоли и включите вход в систему по паролю.

f.	Назначьте cisco в качестве пароля VTY и включите вход в систему по паролю.

g.	Зашифруйте открытые пароли.

h.	Создайте баннер, который предупреждает о запрете несанкционированного доступа.

i.	Настройте и активируйте на коммутаторе интерфейс VLAN 1, используя информацию, приведенную в таблице адресации.

j.	Сохраните текущую конфигурацию в файл загрузочной конфигурации.

![image](https://github.com/user-attachments/assets/82ab7712-26e1-4f02-b85d-d176577f4ca6)

**Шаг 2. Настройте коммутатор для соединения по протоколу SSH.**

Для настройки протокола SSH на коммутаторе используйте те же команды, которые применялись для аналогичной настройки маршрутизатора в части 2.

a.	Настройте имя устройства, как указано в таблице адресации.

b.	Задайте домен для устройства.

c.	Создайте ключ шифрования с указанием его длины.

d.	Создайте имя пользователя в локальной базе учетных записей.

e.	Активируйте протоколы Telnet и SSH на линиях VTY.

f.	Измените способ входа в систему таким образом, чтобы использовалась проверка пользователей по локальной базе учетных записей.

![image](https://github.com/user-attachments/assets/8f9ce225-4d0b-432d-a0e6-a5dfbee19745)


**Шаг 3. Установите соединение с коммутатором по протоколу SSH.**

Запустите программу Tera Term на PC-A, затем установите подключение по протоколу SSH к интерфейсу SVI коммутатора S1.

![image](https://github.com/user-attachments/assets/eb8ef4a1-672f-43d0-b683-68c428d89384)

![image](https://github.com/user-attachments/assets/23c836a3-3a84-4f62-98b4-e7d2876fcd45)

**Часть 4. Настройка протокола SSH с использованием интерфейса командной строки (CLI) коммутатора**

**Шаг 1. Посмотрите доступные параметры для клиента SSH в Cisco IOS.**

Используйте вопросительный знак (?), чтобы отобразить варианты параметров для команды ssh.

![image](https://github.com/user-attachments/assets/36709620-cfe9-4e84-bbba-ec82ccef1663)

**Шаг 2. Установите с коммутатора S1 соединение с маршрутизатором R1 по протоколу SSH.**

a.	Чтобы подключиться к маршрутизатору R1 по протоколу SSH, введите команду –l admin. 

![image](https://github.com/user-attachments/assets/091b72e3-c865-46a1-9398-00ec53e79f1a)

b.	Чтобы вернуться к коммутатору S1, не закрывая сеанс SSH с маршрутизатором R1, нажмите комбинацию клавиш Ctrl+Shift+6. Отпустите клавиши Ctrl+Shift+6 и нажмите x. Отображается приглашение привилегированного режима EXEC коммутатора.

c.	Чтобы вернуться к сеансу SSH на R1, нажмите клавишу Enter в пустой строке интерфейса командной строки. Чтобы увидеть окно командной строки маршрутизатора, нажмите клавишу Enter еще раз.

d.	Чтобы завершить сеанс SSH на маршрутизаторе R1, введите в командной строке маршрутизатора команду exit.

![image](https://github.com/user-attachments/assets/9d0391dd-f898-4ddd-97f9-915287452831)

![image](https://github.com/user-attachments/assets/f6c26554-7a97-4745-bcf7-68519ef76802)


