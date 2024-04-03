#  Прогнозирование заказов такси

## Описание проекта
Компания «Чётенькое такси» собрала исторические данные о заказах такси в аэропортах. Чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час. Постройте модель для такого предсказания.

Значение метрики *RMSE* на тестовой выборке должно быть не больше 48.

## План работы

1. Загрузим данные и выполним их ресемплирование по одному часу.
2. Проанализироваем данные.
3. Обучим разные модели с различными гиперпараметрами. Сделаем тестовую выборку размером 10% от исходных данных.
4. Проверим данные на тестовой выборке и сделаем выводы.

## Описание данных

Признаки:

-	`datetime` — время заказа такси
    
-	`num_orders`(от англ. *number of orders*, «число заказов») — количество заказов

Данные находятся в файле: `/datasets/taxi.csv`

## Общий вывод

1. Загрузили данные заказов такси компании «Чётенькое такси». Данные предоставлены на период с марта по август 2018 года.
2. Выполнили их ресемплирование по одному часу.
2. Проанализировали данные построив распределение количества заказов за весь период, месяц, неделю и день.
3. Изучили закономерности и обнаружили всплески приходящие на выходные и праздничные дни.
3. Обучили модели линейной регрессии, Lasso и Ridge с различными гиперпараметрами сделав тестовую выборку размером 10% от исходных данных.
4. Подобрали гиперпараметры на тествой выборке для каждой модели с минимальным значением метрики RSME. RSME для каждой модели удобвлетворяет требованию иметь значение не больше 48.
5. Лучшей моделью с минимальной метрикой RSME = 38.863 на тестовой выборке показала модель Lasso с максимальным смещением =  157, размером скользящего окна =  1 и коэффициентом регуляризации = 0.1.
