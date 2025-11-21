В качестве сущностей для базы данных на тему «Система аренды автомобилей» были выбраны следующие:

**Пользователь (User):**

user_id (PK);
login (unique)
password_hash;
full_name;
phone;
email;
role_id (FK).
Роль (Role):
role_id (PK);
name (указывается тип роли: клиент, администратор, менеджер).

**Клиент (Client):**
client_id (PK);
user_id (FK, unique);
driver_license_number;
passport_number;
birth_date;

**Администратор (Admin):**
admin_id (PK);
user_id (FK, unique);

**Автомобиль (Car):**
car_id (PK);
brand;
model;
year;
license_plate;
status (доступен / в аренде / в ремонте);
price_per_day;

**Аренда (Rental):**
rental_id (PK);
client_id (FK);
id (FK);
start_date;
end_date;
total_cost;
status (активна / завершена / отменена).

**Платёж (Payment):**
payment_id (PK);
rental_id (FK);
payment_date;
amount;
method (карта, наличные, перевод).

**Повреждение (DamageReport):**
report_id (PK);
rental_id (FK);
description;
repair_cost;
report_date;

**Локация (Location):**
location_id (PK);
name;
address;

**Автомобиль в локации (CarLocation):**
car_location_id (PK);
car_id (FK);
location_id (FK);
arrival_date;
departure_date.

К основным функциям для работы с данными относятся:

**Пользователи:**
регистрация и авторизация (проверка логина и пароля);
просмотр и редактирование профиля;
удаление пользователя;
назначение ролей.

**Клиенты:**
создание клиента;
обновление данных (паспорт, права, контакты);
поиск клиента по имени, телефону, email.

**Автомобили:**
добавление и удаление автомобилей;
изменение статуса (доступен, в аренде, ремонт);
просмотр характеристик и истории аренды.

**Аренды:**

создание аренды (выбор автомобиля, срок, клиент);
завершение или отмена аренды;
просмотр активных и завершённых аренд.

**Платежи:**

регистрация оплаты аренды;
просмотр истории платежей;
расчёт суммы с учётом срока аренды.
Отчёты о повреждениях:
добавление отчёта о повреждении;
просмотр истории ремонтов.

**Локации:**
просмотр и добавление пунктов выдачи;
привязка автомобиля к локации.

<img width="653" height="797" alt="Снимок экрана 2025-11-21 151948" src="https://github.com/user-attachments/assets/7255adfc-7d73-459e-821e-7e59fe9f700d" />
