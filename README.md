# RetailAnalytics v1.0

Загрузка данных по аналитике розничных сетей, их простой анализ, статистика, сегментация клиентов и создание персональных предложений.



#### Таблица Персональные данные

| **Поле**                    | **Название поля в системе** | **Формат / возможные значения**                                                  | **Описание** |
|:---------------------------:|:---------------------------:|:--------------------------------------------------------------------------------:|:------------:|
| Идентификатор клиента       | Customer_ID                 | ---                                                                              | ---          |
| Имя                         | Customer_Name               | Кириллица или латиница, первая буква заглавная, остальные прописные, допустимы тире и пробелы | ---          |
| Фамилия                     | Customer_Surname            | Кириллица или латиница, первая буква заглавная, остальные прописные, допустимы тире и пробелы | ---          |
| E-mail клиента              | Customer_Primary_Email      | Формат E-mail                                                                    | ---          |
| Телефон клиента             | Customer_Primary_Phone      | +7 и 10 арабских цифр                                                                 | ---          |

#### Таблица Карты

| **Поле**              | **Название поля в системе** | **Формат / возможные значения** | **Описание**                                     |
|:---------------------:|:---------------------------:|:-------------------------------:|:------------------------------------------------:|
| Идентификатор карты   | Customer_Card_ID            | ---                             | ---                                              |
| Идентификатор клиента | Customer_ID                 | ---                             | Одному клиенту может принадлежать несколько карт |

#### Таблица Транзакции

| **Поле**                 | **Название поля в системе** | **Формат / возможные значения** | **Описание**                                                          |
|:------------------------:|:---------------------------:|:-------------------------------:|:---------------------------------------------------------------------:|
| Идентификатор транзакции | Transaction_ID              | ---                             | Уникальное значение                                                   |
| Идентификатор карты      | Customer_Card_ID            | ---                             | ---                                                                   |
| Сумма транзакции         | Transaction_Summ            | Арабская цифра                  | Сумма транзакции в рублях (полная стоимость покупки без учета скидок) |
| Дата транзакции          | Transaction_DateTime        | дд.мм.гггг чч:мм:сс             | Дата и время совершения транзакции                                    |
| Торговая точка           | Transaction_Store_ID        | Идентификатор магазина          | Магазин, в котором была совершена транзакция                          |

#### Таблица Чеки

| **Поле**                            | **Название поля в системе** | **Формат / возможные значения** | **Описание**                                                                                            |
|:-----------------------------------:|:---------------------------:|:-------------------------------:|:-------------------------------------------------------------------------------------------------------:|
| Идентификатор транзакции            | Transaction_ID              | ---                             | Идентификатор транзакции указывается для всех позиций в чеке                                            |
| Позиция в чеке                      | SKU_ID                      | ---                             | ---                                                                                                     |
| Количество штук или килограмм       | SKU_Amount                  | Арабская цифра                  | Указание, какое количество товара было куплено                                                          |
| Сумма, на которую был куплен товар  | SKU_Summ                    | Арабская цифра                  | Сумма покупки фактического объема данного товара в рублях (полная стоимость без учета скидок и бонусов) |
| Оплаченная стоимость покупки товара | SKU_Summ_Paid               | Арабская цифра                  | Фактически оплаченная сумма покупки данного товара, не включая сумму предоставленной скидки             |
| Предоставленная скидка              | SKU_Discount                | Арабская цифра                  | Размер предоставленной на товар скидки в рублях                                                         |

#### Таблица Товарная матрица

| **Поле**                    | **Название поля в системе** | **Формат / возможные значения**        | **Описание**                                                                                                                                                                                                 |
|:---------------------------:|:---------------------------:|:--------------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| Идентификатор товара        | SKU_ID                      | ---                                    | ---                                                                                                                                                                                                          |
| Название товара             | SKU_Name                    | Кириллица или латиница, арабские цифры, спецсимволы | ---                                                                                                                                                                                                          |
| Группа SKU                  | Group_ID                    | ---                                    | Идентификатор группы родственных товаров, к которой относится товар (например, одинаковые йогурты одного производителя и объема, но разных вкусов). Указывается один идентификатор для всех товаров в группе |

#### Таблица Торговые точки

| **Поле**                    | **Название поля в системе** | **Формат / возможные значения** | **Описание**                                                   |
|:---------------------------:|:---------------------------:|:-------------------------------:|:--------------------------------------------------------------:|
| Торговая точка              | Transaction_Store_ID        | ---                             | ---                                                            |
| Идентификатор товара        | SKU_ID                      | ---                             | ---                                                            |
| Закупочная стоимость товара | SKU_Purchase_Price          | Арабская цифра                  | Закупочная стоимость товара для данного магазина               |
| Розничная стоимость товара  | SKU_Retail_Price            | Арабская цифра                  | Стоимость продажи товара без учета скидок для данного магазина |

#### Таблица Группы SKU

| **Поле**                    | **Название поля в системе** | **Формат / возможные значения**        | **Описание** |
|:---------------------------:|:---------------------------:|:--------------------------------------:|:------------:|
| Группа SKU                  | Group_ID                    | ---                                    | ---          |
| Название группы             | Group_Name                  | Кириллица или латиница, арабские цифры, спецсимволы | ---          |

#### Таблица Дата формирования анализа

| **Поле**                    | **Название поля в системе** | **Формат / возможные значения**        | **Описание** |
|:---------------------------:|:---------------------------:|:--------------------------------------:|:------------:|
| Дата формирования анализа                  | Analysis_Formation                    | дд.мм.гггг чч:мм:сс                                    | ---          |

### Выходные данные

#### Представление Клиенты

| **Поле**                                    | **Название поля в системе**    | **Формат / возможные значения**  | **Описание**                                                                  |
|:-------------------------------------------:|:------------------------------:|:--------------------------------:|:-----------------------------------------------------------------------------:|
| Идентификатор клиента                       | Customer_ID                    | ---                              | Уникальное значение                                                           |
| Значение среднего чека                      | Customer_Average_Check         | Арабская цифра, десятичная дробь | Значение среднего чека клиента в рублях за анализируемый период               |
| Сегмент по среднему чеку                    | Customer_Average_Check_Segment | Высокий; Средний; Низкий         | Описание сегмента                                                             |
| Значение частоты транзакций                 | Customer_Frequency             | Арабская цифра, десятичная дробь | Значение частоты визитов клиента в среднем количестве дней между транзакциями |
| Сегмент по частоте транзакций               | Customer_Frequency_Segment     | Часто; Средне; Редко             | Описание сегмента                                                             |
| Количество дней после предыдущей транзакции | Customer_Inactive_Period       | Арабская цифра, десятичная дробь | Количество дней, прошедших с даты предыдущей транзакции клиента               |
| Коэффициент оттока                          | Customer_Churn_Rate            | Арабская цифра, десятичная дробь | Значение коэффициента оттока клиента                                          |
| Сегмент по коэффициенту оттока              | Customer_Churn_Segment         | Высокий; Средний; Низкий         | Описание сегмента                                                             |
| Номер сегмента                              | Customer_Segment               | Арабская цифра                   | Номер сегмента, к которому принадлежит клиент                                 |
| Идентификатор основного магазина            | Customer_Primary_Store         | ---                              | ---                                                                           |

#### Представление История покупок

| **Поле**                        | **Название поля в системе** | **Формат / возможные значения**  | **Описание**                                                                                                                                                                                                 |
|:-------------------------------:|:---------------------------:|:--------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| Идентификатор клиента           | Customer_ID                 | ---                              | ---                                                                                                                                                                                                          |
| Идентификатор транзакции        | Transaction_ID              | ---                              | ---                                                                                                                                                                                                          |
| Дата транзакции                 | Transaction_DateTime        | гггг-мм-ддTчч:мм:сс.0000000      | Дата совершения транзакции                                                                                                                                                                                   |
| Группа SKU                      | Group_ID                    | ---                              | Идентификатор группы родственных товаров, к которой относится товар (например, одинаковые йогурты одного производителя и объема, но разных вкусов). Указывается один идентификатор для всех товаров в группе |
| Себестоимость                   | Group_Cost                  | Арабская цифра, десятичная дробь | ---                                                                                                                                                                                                          |
| Базовая розничная стоимость     | Group_Summ                  | Арабская цифра, десятичная дробь | ---                                                                                                                                                                                                          |
| Фактически оплаченная стоимость | Group_Summ_Paid             | Арабская цифра, десятичная дробь | ---                                                                                                                                                                                                          |

#### Представление Периоды

| **Поле**                            | **Название поля в системе** | **Формат / возможные значения**  | **Описание**                                                                                                                                                                                                 |
|:-----------------------------------:|:---------------------------:|:--------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| Идентификатор клиента               | Customer_ID                 | ---                              | ---                                                                                                                                                                                                          |
| Идентификатор группы SKU            | Group_ID                    | ---                              | Идентификатор группы родственных товаров, к которой относится товар (например, одинаковые йогурты одного производителя и объема, но разных вкусов). Указывается один идентификатор для всех товаров в группе |
| Дата первой покупки группы          | First_Group_Purchase_Date   | гггг-мм-ддTчч:мм:сс.0000000      | ---                                                                                                                                                                                                          |
| Дата последней покупки группы       | Last_Group_Purchase_Date    | гггг-мм-ддTчч:мм:сс.0000000      | ---                                                                                                                                                                                                          |
| Количество транзакций с группой     | Group_Purchase              | Арабская цифра, десятичная дробь | ---                                                                                                                                                                                                          |
| Интенсивность покупок группы        | Group_Frequency             | Арабская цифра, десятичная дробь | ---                                                                                                                                                                                                          |
| Минимальный размер скидки по группе | Group_Min_Discount          | Арабская цифра, десятичная дробь | ---                                                                                                                                                                                                          |

#### Представление Группы

| **Поле**                   | **Название поля в системе** | **Формат / возможные значения**  | **Описание**                                                                                                                        |
|:--------------------------:|:---------------------------:|:--------------------------------:|:-----------------------------------------------------------------------------------------------------------------------------------:|
| Идентификатор клиента      | Customer_ID                 | ---                              | ---                                                                                                                                 |
| Идентификатор группы       | Group_ID                    | ---                              | ---                                                                                                                                 |
| Индекс востребованности    | Group_Affinity_Index        | Арабская цифра, десятичная дробь | Коэффициент востребованности данной группы клиентом                                                                                 |
| Индекс оттока              | Group_Churn_Rate            | Арабская цифра, десятичная дробь | Индекс оттока клиента по конкретной группе                                                                                          |
| Индекс стабильности        | Group_Stability_Index       | Арабская цифра, десятичная дробь | Показатель, демонстрирующий стабильность потребления группы клиентом                                                                |
| Актуальная маржа по группе | Group_Margin                | Арабская цифра, десятичная дробь | Показатель актуальной маржи по группе для конкретного клиента                                                                       |
| Доля транзакций со скидкой | Group_Discount_Share        | Арабская цифра, десятичная дробь | Доля транзакций по покупке группы клиентом, в рамках которых были применена скидка (без учета списания бонусов программы лояльности) |
| Минимальный размер скидки  | Group_Minimum_Discount      | Арабская цифра, десятичная дробь | Минимальный размер скидки, зафиксированный для клиента по группе                                                                    |
| Средний размер скидки      | Group_Average_Discount      | Арабская цифра, десятичная дробь | Средний размер скидки по группе для клиента                                                                                         |


## Chapter III

## Part 1. Создание базы данных

Напишите скрипт *part1.sql*, создающий базу данных и таблицы, описанные выше в разделе [входные данные](#входные-данные).

Также внесите в скрипт процедуры, позволяющие импортировать и экспортировать данные для каждой таблицы из файлов/в файлы с расширением *.csv* и *.tsv*. \
В качестве параметра каждой процедуры для импорта из *csv* файла указывается разделитель.

В каждую из таблиц внесите как минимум по 5 записей.
По мере выполнения задания вам потребуются новые данные, чтобы проверить все варианты работы.
Эти новые данные также должны быть добавлены в этом скрипте. \
Некоторые тестовые данные могут быть найдены в папке *datasets*.

Если для добавления данных в таблицы использовались *csv* или *tsv* файлы, они также должны быть выгружены в GIT репозиторий.

## Part 2. Создание представлений

Создайте скрипт *part2.sql*, в котором напишите представления, описанные выше в разделе [выходные данные](#выходные-данные).
Также внесите в скрипт тестовые запросы для каждого представления. Допустимо для каждого представления создавать отдельный скрипт, начинающийся с *part2_*.

Более подробную информацию для получения каждого поля можно найти в папке materials.

## Part 3. Ролевая модель

Внесите в скрипт *part3.sql* создание ролей и выдачу им прав в соответствии с описанным ниже.

####  Администратор
Администратор имеет полные права на редактирование и просмотр
любой информации, запуск и остановку процесса обработки.

####  Посетитель
Только просмотр информации из всех таблиц.

## Part 4. Формирование персональных предложений, ориентированных на рост среднего чека

Создайте скрипт *part4.sql*, в который внесите описанную далее функцию.

### Написать функцию, определяющую предложения, ориентированные на рост среднего чека

Параметры функции:
- метод расчета среднего чека (1 - за период, 2 - за количество)
- первая и последняя даты периода (для 1 метода)
- количество транзакций (для 2 метода)
- коэффициент увеличения среднего чека
- максимальный индекс оттока
- максимальная доля транзакций со скидкой (в процентах)
- допустимая доля маржи (в процентах)

##### Определение условия предложения

1.  **Выбор метода расчета среднего чека.** Существует возможность
    выбора метода расчета среднего чека – за определенный период времени
    или за определенное количество последних транзакций. Метод расчета
    *вручную определяется* пользователем.

    1.  Пользователь выбирает методику расчета **по периоду**, после чего
        указывает первую и последнюю даты периода, за который
        необходимо рассчитать средний чек для всей совокупности
        клиентов, попавших в выборку. При этом последняя дата
        указываемого периода должна быть позже первой, а указанный
        период должен быть внутри общего анализируемого периода. В
        случае указания слишком ранней или слишком поздней даты
        система автоматически подставляет дату, соответственно, начала
        или окончания анализируемого периода. Для расчета учитываются
        все транзакции, совершенные каждым конкретным клиентом в
        течение заданного периода.

    2.  Пользователь выбирает методику расчета **по количеству последних
        транзакций**, после чего вручную указывает количество
        транзакций, по которым необходимо рассчитать средний чек. Для
        расчета среднего чека берется заданное пользователем
        количество транзакций, начиная с самой последней в обратном
        хронологическом порядке. В случае, если каким-либо клиентом из
        выборки за весь анализируемый период совершено меньше
        указанного количества транзакций, для анализа используется
        имеющееся количество транзакций.

2.  **Определение среднего чека.** Для каждого клиента определяется
    текущее значение его среднего чека согласно выбранному в рамках шага
    1 методу. Для этого общий товарооборот по всем попавшим в выборку
    транзакциям клиента делится на количество этих транзакций. Итоговое
    значение сохраняется в таблице как текущее значение среднего чека.

3.  **Определение целевого значения среднего чека.** Рассчитанное
    значение среднего чека умножается на коэффициент заданный пользователем. Получившееся значение сохраняется в системе
    как целевое значение среднего чека клиента и в дальнейшем
    используется для формирования условия предложения, которое должен
    выполнить клиент для получения вознаграждения.

##### Определение вознаграждения

4.  **Определение группы для формирования вознаграждения.** Для
    формирования вознаграждения выбирается группа, отвечающая
    последовательно следующим критериям:

    -   Индекс востребованности группы – максимальный из всех возможных.

    -   Индекс оттока по данной группе не должен превышать заданного пользователем значения. В случае, если коэффициент оттока превышает
        установленное значение, берется следующая по индексу
        востребованности группа;

    -   Доля транзакций со скидкой по данной группе – менее заданного пользователем значения. В случае, если для выбранной группы превышает
        установленное значение, берется следующая по индексу
        востребованности группа, удовлетворяющая также критерию по
        оттоку.

5.  **Определение максимально допустимого размера скидки для
    вознаграждения.** Пользователь вручную определяет долю маржи (в
    процентах), которую допустимо использовать для предоставления
    вознаграждения по группе. Итоговое значение максимально допустимой
    скидки рассчитывается путем умножения заданного значения на среднюю
    маржу клиента по группе.

6.  **Определение величины скидки.** Значение, полученное на шаге 5,
    сравнивается с минимальной скидкой, которая была зафиксирована для
    клиента по данной группе, округленной вверх с шагом в 5%. В случае,
    если минимальная скидка после округления меньше значения,
    получившегося на шаге 5, она устанавливается в качестве скидки для
    группы в рамках предложения для клиента. В противном случае данная
    группа исключается из рассмотрения, и для формирования предложения
    для клиента процесс повторяется, начиная с шага 4 (используются
    следующая подходящая по описанным критериям группа).

Вывод функции:

| **Поле**                       | **Название поля в системе** | **Формат / возможные значения**            | **Описание**                                                                               |
|--------------------------------|-----------------------------|--------------------------------------------|--------------------------------------------------------------------------------------------|
| Идентификатор клиента          | Customer_ID                 |                                            |                                                                                            |
| Целевое значение среднего чека | Required_Check_Measure      | Арабская цифра (десятичная дробь)          | Целевое значение среднего чека, необходимое для получения вознаграждения                   |
| Группа предложения             | Group_Name                  |                                            | Название группы предложения, на которой начисляется вознаграждение при выполнении условия. |
| Максимальная глубина скидки    | Offer_Discount_Depth        | Арабская цифра (десятичная дробь), процент | Максимально возможный размер скидки для предложения                                        |

## Part 5. Формирование персональных предложений, ориентированных на рост частоты визитов

Создайте скрипт *part5.sql*, в который внесите описанную далее функцию.

### Написать функцию, определяющую предложения, ориентированные на рост частоты визитов
Параметры функции:
- первая и последняя даты периода
- добавляемое число транзакций
- максимальный индекс оттока
- максимальная доля транзакций со скидкой (в процентах)
- допустимая доля маржи (в процентах)

##### Определение условия предложения

1. **Определение периода.** Пользователь вручную задает период действия разрабатываемого предложения, указывая первую и конечную его даты.

2. **Определение текущей частоты посещений клиента в заданный период.**
   Из конечной даты заданного периода вычитается первая дата,
   после чего полученное значение делится на среднюю интенсивность транзакций клиента (поле `Customer_Frequency` [таблицы Клиенты](#представление-клиенты)).
   Итоговый результат сохраняется в качестве базовой интенсивности транзакций клиента в течение заданного периода.

3. **Определение транзакции для начисления вознаграждения.**
   Система определяет порядковый номер транзакции в рамках заданного периода, на которую должно быть начислено вознаграждение.
   Для этого значение, полученное на шаге 2, округляется согласно арифметическим правилам до целого,
   после чего к нему добавляется число транзакций, заданное пользователем.
   Итоговое значение является целевым количеством транзакций, которое должен совершить клиент для получения вознаграждения.

##### Определение вознаграждения

4.  **Определение группы для формирования вознаграждения.** Для
    формирования вознаграждения выбирается группа, отвечающая
    последовательно следующим критериям:

    -  Индекс востребованности группы – максимальный из всех возможных.

    -  Индекс оттока по данной группе не должен превышать заданного пользователем значения. В случае, если коэффициент оттока превышает
       установленное значение, берется следующая по индексу
       востребованности группа;

    -  Доля транзакций со скидкой по данной группе – менее заданного пользователем значения. В случае, если для выбранной группы превышает
       установленное значение, берется следующая по индексу
       востребованности группа, удовлетворяющая также критерию по
       оттоку.

5.  **Определение максимально допустимого размера скидки для
    вознаграждения.** Пользователь вручную определяет долю маржи (в
    процентах), которую допустимо использовать для предоставления
    вознаграждения по группе. Итоговое значение максимально допустимой
    скидки рассчитывается путем умножения заданного значения на среднюю
    маржу клиента по группе.

6.  **Определение величины скидки.** Значение, полученное на шаге 5,
    сравнивается с минимальной скидкой, которая была зафиксирована для
    клиента по данной группе, округленной вверх с шагом в 5%. В случае,
    если минимальная скидка после округления меньше значения,
    получившегося на шаге 5, она устанавливается в качестве скидки для
    группы в рамках предложения для клиента. В противном случае данная
    группа исключается из рассмотрения, и для формирования предложения
    для клиента процесс повторяется, начиная с шага 4 (используются
    следующая подходящая по описанным критериям группа).

Вывод функции:

| **Поле**                      | **Название поля в системе** | **Формат / возможные значения**            | **Описание**                                                                               |
|-------------------------------|-----------------------------|--------------------------------------------|--------------------------------------------------------------------------------------------|
| Идентификатор клиента         | Customer_ID                 |                                            |                                                                                            |
| Дата начала периода           | Start_Date                  | гггг-мм-ддTчч:мм:сс.0000000                | Дата начала периода, в течение которого необходимо совершить транзакции                    |
| Дата окончания периода        | End_Date                    | гггг-мм-ддTчч:мм:сс.0000000                | Дата окончания периода, в течение которого необходимо совершить транзакции                 |
| Целевое количество транзакций | Required_Transactions_Count | Арабская цифра (десятичная дробь)          | Порядковый номер транзакции, на которую начисляется вознаграждение                         |
| Группа предложения            | Group_Name                  |                                            | Название группы предложения, на которой начисляется вознаграждение при выполнении условия. |
| Максимальная глубина скидки   | Offer_Discount_Depth        | Арабская цифра (десятичная дробь), процент | Максимально возможный размер скидки для предложения                                        |

## Part 6. Формирование персональных предложений, ориентированных на кросс-продажи

Создайте скрипт *part6.sql*, в который внесите описанную далее функцию.

### Написать функцию, определяющую предложения, ориентированные на кросс-продажи (рост маржи)
Параметры функции:
- количество групп
- максимальный индекс оттока
- максимальный индекс стабильности потребления
- максимальная доля SKU (в процентах)
- допустимая доля маржи (в процентах)

Предложения, ориентированные на рост маржи за счет кросс-продаж,
подразумевают переключение клиента на максимально маржинальное SKU в
рамках востребованной им группы.

1.  **Выбор групп.** Для формирования предложений, ориентированных на
    рост маржи за счет кросс-продаж, для каждого клиента выбирается несколько
    групп (количество *задается* пользователем) с
    максимальным индексом востребованности, отвечающие следующим
    условиям:

    1.  Индекс оттока по группе не более заданного пользователем значения.

    2.  Индекс стабильности потребления группы составляет менее заданного пользователем значения.

2.  **Определение SKU с максимальной маржой.** В каждой группе
    определяется SKU с максимальной маржой (в рублях). Для этого по
    основному магазину клиента из розничной цены товара
    (`SKU_Retail_Price`) вычитается его закупочная стоимость
    (`SKU_Purchase_Price`) для всех SKU данной группы, представленных
    в магазине, после чего выбирается одно SKU с максимальным
    значением указанной разницы.

3.  **Определение доли SKU в группе.** Определяется доля транзакций, в
    которых присутствует анализируемое SKU. Для этого количество
    транзакций, содержащих данный SKU, делится на количество
    транзакций, содержащих группу в целом (за анализируемый период).
    SKU используется для формирования предложения только в том случае,
    если получившееся значение не превышает заданного пользователем значения.

4.  **Определение доли маржи для расчета скидки.** Пользователь *вручную
    определяет* долю маржи (в процентах), которую допустимо
    использовать для предоставления вознаграждения по SKU (задается
    единое значение для всей совокупности клиентов).

5.  **Расчет скидки.** *Заданное* пользователем на шаге 4 значение
    умножается на разницу между розничной (`SKU_Retail_Price`) и
    закупочной (`SKU_Purchase_Price`) ценой, а получившееся значение
    делится на розничную цену SKU (`SKU_Retail_Price`). Все цены – для
    основного магазина клиента. В случае, если получившееся значение
    равно или превышает минимальный размер скидки пользователя для
    анализируемой группы, округленной вверх с шагом в 5%, то в
    качестве скидки для данного SKU для клиента устанавливается
    минимальная скидка для группы, округленная вверх с шагом в 5%. В
    противном случае для клиента не формируется предложение по данной
    группе.

Вывод функции:

| **Поле**                    | **Название поля в системе** | **Формат / возможные значения**            | **Описание**                                                                            |
|-----------------------------|-----------------------------|--------------------------------------------|-----------------------------------------------------------------------------------------|
| Идентификатор клиента       | Customer_ID                 |                                            |                                                                                         |
| SKU предложения             | SKU_Name                    |                                            | Название SKU предложения, на который начисляется вознаграждение при выполнении условия. |
| Максимальная глубина скидки | Offer_Discount_Depth        | Арабская цифра (десятичная дробь), процент | Максимально возможный размер скидки для предложения                                     |


## Chapter IV

Чак уже несколько часов смотрел на экран и не мог понять. Некий отдел "РАИ" пропадает из отчетов так же быстро, как появляется, буквально в мгновение ока. 
Все траты списываются на разработку умных пылесосов, но ими издавна занимается только бытовой отдел. Да, в это время был выход новой модели СП-21, но все же что это: невинная опечатка в названии или же удобный момент? Вопрос, который будет гложить Чака все ближайшее время..

💡 [Нажми тут](https://forms.yandex.ru/u/635ab5be84227c207a24b1b6/), **чтобы поделиться с нами обратной связью на этот проект**. Это анонимно и поможет команде Педаго сделать твоё обучение лучше.
