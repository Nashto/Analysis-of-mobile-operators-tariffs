# Анализ тарифов сотовой связи
Определение прибыльного тарифа, на которой стоит сделать акцент при работе над рекламной компанией

Анализ тарифов сотовой 

Клиентам предлагается два тарифных плана: «Смарт» и «Ультра». Чтобы скорректировать рекламный бюджет, коммерческий департамент хочет понять, какой тариф приносит больше денег.
Необходимо сделать предварительный анализ тарифов на небольшой выборке клиентов. В распоряжении имеются данные 500 пользователей оператора: кто они, откуда, каким тарифом пользуются, сколько звонков и сообщений каждый отправил за 2018 год. 
Нужно проанализировать поведение клиентов и сделать вывод — какой тариф лучше.

Описание тарифов

Тариф «Смарт»
1.	Ежемесячная плата: 550 рублей
2.	Включено 500 минут разговора, 50 сообщений и 15 Гб интернет-трафика
3.	Стоимость услуг сверх тарифного пакета: 1. минута разговора: 3 рубля («Мегалайн» всегда округляет вверх значения минут и мегабайтов. Если пользователь проговорил всего 1 секунду, в тарифе засчитывается целая минута); 2. сообщение: 3 рубля; 3. 1 Гб интернет-трафика: 200 рублей.
Тариф «Ультра»
1.	Ежемесячная плата: 1950 рублей
2.	Включено 3000 минут разговора, 1000 сообщений и 30 Гб интернет-трафика
3.	Стоимость услуг сверх тарифного пакета: 1. минута разговора: 1 рубль; 2. сообщение: 1 рубль; 3. 1 Гб интернет-трафика: 150 рублей.

Примечание:
Оператор сотовой связи всегда округляет секунды до минут, а мегабайты — до гигабайт. Каждый звонок округляется отдельно: даже если он длился всего 1 секунду, будет засчитан как 1 минута.
Для веб-трафика отдельные сессии не считаются. Вместо этого общая сумма за месяц округляется в бо́льшую сторону. Если абонент использует 1025 мегабайт в этом месяце, с него возьмут плату за 2 гигабайта.

Описание данных

Таблица users (информация о пользователях):
•	user_id — уникальный идентификатор пользователя
•	first_name — имя пользователя
•	last_name — фамилия пользователя
•	age — возраст пользователя (годы)
•	reg_date — дата подключения тарифа (день, месяц, год)
•	churn_date — дата прекращения пользования тарифом (если значение пропущено, то тариф ещё действовал на момент выгрузки данных)
•	city — город проживания пользователя
•	tarif — название тарифного плана

Таблица calls (информация о звонках):
•	id — уникальный номер звонка
•	call_date — дата звонка
•	duration — длительность звонка в минутах
•	user_id — идентификатор пользователя, сделавшего звонок

Таблица messages (информация о сообщениях):
•	id — уникальный номер сообщения
•	message_date — дата сообщения
•	user_id — идентификатор пользователя, отправившего сообщение

Таблица internet (информация об интернет-сессиях):
•	id — уникальный номер сессии
•	mb_used — объём потраченного за сессию интернет-трафика (в мегабайтах)
•	session_date — дата интернет-сессии
•	user_id — идентификатор пользователя

Таблица tariffs (информация о тарифах):
•	tariff_name — название тарифа
•	rub_monthly_fee — ежемесячная абонентская плата в рублях
•	minutes_included — количество минут разговора в месяц, включённых в абонентскую плату
•	messages_included — количество сообщений в месяц, включённых в абонентскую плату
•	mb_per_month_included — объём интернет-трафика, включённого в абонентскую плату (в мегабайтах)
•	rub_per_minute — стоимость минуты разговора сверх тарифного пакета (например, если в тарифе 100 минут разговора в месяц, то со 101 минуты будет взиматься плата)
•	rub_per_message — стоимость отправки сообщения сверх тарифного пакета
•	rub_per_gb — стоимость дополнительного гигабайта интернет-трафика сверх тарифного пакета (1 гигабайт = 1024 мегабайта)
