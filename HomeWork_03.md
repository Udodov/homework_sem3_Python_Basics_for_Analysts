# Практическое задание 3. «Изменение таблиц в Pandas»
*Обновлено xx.xx.xxxx*

Усложнение задач выделены ```(*)```. Они необязательны для решения и нужны для тех, кому мало выполнить обычное задание.
Если вы хотите решить усложненное задание - сначала сделайте задание обычной сложности.


#### 3.1. Работа с датасетом "house price"

- Скачать данные по ссылке https://www.kaggle.com/datasets/esratmaria/house-price-dataset-with-other-information
- Описание датасета
- Считать данные с помощью pandas
- Вывести на экран первые 5 строк
1.1 Создать новый признак price_per_sq_lot, который будет содержать стоимость за один кв. метр общей площади
1.2 Создать новый признак delta_renovated, который будет содержать разницу в годах между годом реновацией дома и годом постройки дома. Если реновации дома не было, то в новом признаке поставьте 0
1.3 Создайте признаки года продажи, месяца продажи
1.4 Удалите признаки date, zipcode, lat, long

```
    - id - Уникальный ID для каждого дома
    - date - Дата продажи дома
    - price - Стоимость продажи дома
    - bedrooms - Кол-во спален
    - bathrooms - Кол-во ванных комнат (0.5 - туалет без душа)
    - sqft_living - Кв. метры жилые
    - sqft_lot - Кв. метры общие
    - floors - Кол-во этажей
    - waterfront - Есть набержная или нет
    - view - Значение от 0 до 4 насколько хороший вид
    - condition - Значение от 1 до 5 насколько хорошее состояние
    - grade - Значение от 1 до 13, где 1-3 плохая конструкция здания и дизайн, 7 - средний уровень конструкции и дизайна, 11-13 - высокое качество конструкции и дизайна
    - sqft_above - Кв. метры дома, которые находятся выше земли
    - sqft_basement - Кв. метры дома, которые находятся ниже земли
    - yr_built - Год постройки дома
    - yr_renovated - Год ремонта дома
    - zipcode - Индекс
    - lat - Широтма
    - long - Долгота
    - sqft_living15 - Кв. метры жилой площади у 15 соседей
    - sqft_lot15 - Кв. метры общей площади у 15 соседей
```

#### 3.2. Работа с датасетом "клиенты" и "house price" - слияние данных

Создайте датафрейм с клиентами:
```
    clients = pd.DataFrame({ 
            'client_id': [1459, 4684, 3498, 3942, 4535, 2308, 2866, 2765, 1472, 4236, 2295, 939, 3840,  280,   20, 4332, 3475, 4213, 3113, 4809, 2134, 2242, 2068, 4929, 1384, 1589, 3317, 2260, 1727, 1764, 1611, 1474],
            'house_id': [8965450190, 6823100225, 5104540330, 2131701075, 1522700060, 1189000207, 6821600300, 7137950720, 9510920050, 6131600255, 5428000070, 1788800910, 8100400160, 3123049142, 6306800010, 5083000375, 7920100025, 1951600150,  809001400,  339600110, 1622049154, 1099600250, 8563000110, 2768100205, 3995700435, 8861700030, 3303980210, 7731100066, 8146100580,  825069097, 3889100029, 9524100196]
})
```
house_id - это признак id в датафрейме с домами (задание 1)
2.1 Присоедините к таблице clients данные по домам через метод join
2.2 Присоедините к таблице clients данные по домам через метод merge

#### 3.3. Составьте несколько сводных таблиц
3.1 Найдите среднюю стоимость домов в зависимости от количества спален. Отсортируйте от меньшей стоимости к большей
3.2 Найдите минимальную, среднюю и максимальную стоимости домов в зависимости от состояния дома
3.3 Постройте таблицу с подсчетом количества домов в данных в зависимости от вида на набережную и оценкой вида
3.4 Каких домов в зависимости от этажности и количества спален больше?
3.5 Постройте таблицу с подсчетом медианной стоимости домов в данных в зависимости от состояния дома и оценки дома