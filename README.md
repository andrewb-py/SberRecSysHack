# SberRecSysHack
Построение кросс-доменной рекомендательной системы для СберМаркета и СберЗвука для хакатона
Датасеты: https://www.kaggle.com/datasets/andrewbaevsky/sber-recsys-hack/data

Задача:
Рекомендательные системы плотно вошли в нашу жизнь. Их постоянное развитие позволяет нам с легкостью найти нужный товар, музыку под настроение или подходящий под момент фильм для просмотра, а их владельцам - генерировать миллиардный дополнительный доход. Одним из передовых направлений в развитии рекомендательных систем является построение кросс-доменных рекомендаций - когда, например, по действиям пользователя в интернет-магазине необходимо понять, какой плейлист для прослушивания в стриминговом сервисе ему предложить в данный момент
Посмотрим, сможете ли вы предложить алгоритм рекомендаций, работающий лучше, чем МЛ-алгоритмы от разработчиков рекомендательной системы Сбера. В качестве данных для обучения будем использовать реальные данные экосистемы Сбера - интеракции пользователей на сервисах МегаМаркет и Звук.

датасет о закупках на маркетплейсе МегаМаркет за последние 4 месяца megamaket.parquet: взаимодействий 196,644,020, пользователей 2,730,776, товаров 3,562,321
колонки:
user_id - int32, идентификатор пользователя;
datetime - datetime, дата и время взаимодействия;
event - int32, тип события (0 - клик, 1 - добавление в корзину, 2 - покупка);
item_id - int32, идентификатор товара;
category_id - int32, идентификатор категории товара;
price - float32, цена товара.

датасет о прослушиваниях треков на сервисе Zvuk за последние 4 месяца zvuk-interactions.parquet: взаимодействий 244,673,551, пользователей 382,790, айтемов 1,506,950
колонки:
user_id - int32,идентификатор пользователя;
session_id - идентификатор сессии;
datetime - datetime, дата и время взаимодействия;
track_id - int32, идентификатор трека;
play_duration - float32, длительность прослушивания в секундах.

датасет с информацией о треках zvuk-track_artist_embedding.parquet: кол-во треков 1506950, кол-во артистов 262087
колонки:
track_id - int32, идентификатор трека;
artist_id - int32, идентификатор артиста;
cluster_id - int32, идентификатор кластера трека;
vector - Array(float32), эмбеддинг трека размером 128.
