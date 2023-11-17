# Анализ данных в разработке игр
Отчет по лабораторной работе #3 выполнил(а):
- Бабаев Тимур Ахмадалиевич
- РИ-220912
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | - |
| Задание 2 | * | - |
| Задание 3 | * | - |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1. Предложите вариант изменения найденных переменных для 10 уровней в игре. Визуализируйте изменение уровня сложности в таблице. 
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2. Создайте 10 сцен на Unity с изменяющимся уровнем сложности.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3. Решение в 80+ баллов должно заполнять google-таблицу данными из Python. В Python данные также должны быть визуализированы.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
Разработать оптимальный баланс для десяти уровней игры Dragon Picker

## Задание 1
### Предложите вариант изменения найденных переменных для 10 уровней в игре. Визуализируйте изменение уровня сложности в таблице. 
Я решил изменять сложность уровней линейно, убавлять и прибавлять к переменным фиксированные значения.
Основные факторы сложности в игре это скорость дракона и время между выбросом яиц. Таким образом, чем выше скорость дракона и ниже время между выбросом яиц, тем сложнее.
Ссылка на таблицу: https://docs.google.com/spreadsheets/d/16Os_LCWfanTFVv6ycH8x9nMWI_ltcno2nXkjPIrY-5w/edit#gid=0

Визуализация данных:

![image](https://github.com/truefolder/AD_ingamedev_lab3/assets/89926388/f413f34c-e740-424c-8b48-3031c95b9406)


## Задание 2
### Создайте 10 сцен на Unity с изменяющимся уровнем сложности.
Ознакомиться с созданными мною сценами в Unity вы можете в директории dragonpicker этого репозитория
https://github.com/truefolder/AD_ingamedev_lab3/tree/main/dragonpicker/Assets/_Scenes

## Задание 3
### Решение в 80+ баллов должно заполнять google-таблицу данными из Python. В Python данные также должны быть визуализированы.

Скрипт на python, заполняющий таблицу из первого задания данными:
```python
import gspread
import numpy as np
gc = gspread.service_account(filename='stalwart-edge-361617-65c49b91499f.json')
sh = gc.open("Dragon Picker")
speed = 4
time_between_egg_drops = 2
left_right_distance = 10
chance_direction = 0.01
i = 2
while i <= 11:
    sh.sheet1.update(('B' + str(i)), str(speed))
    sh.sheet1.update(('C' + str(i)), str(round(time_between_egg_drops, 3)))
    sh.sheet1.update(('D' + str(i)), str(left_right_distance))
    sh.sheet1.update(('E' + str(i)), str(round(chance_direction, 3)))
    speed += 1
    time_between_egg_drops -= 0.1
    left_right_distance += 1
    chance_direction += 0.05
    i += 1
```
## Выводы
Я разработал по моим меркам оптимальный баланс для десяти уровней игры Dragon Picker. Научился визуализировать сложность игровых уровней. Научился самостоятельно писать скрипт на заполнение гугл-таблиц и визуализировать данные в python

| Plugin | README |
| ------ | ------ |
| GitHub | [plugins/github/README.md][PlGh] |
| Visual Studio| [plugins/visualstudio/README.md][PlGh] |
| Unity | [plugins/unity/README.md][PlMe] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
