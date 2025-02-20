# Прог. Лабораторная работа №1
###   Знакомство
## 00_distance
### Дан словарь с координатами городов. При помощи формулы - ((x1 - x2) ** 2 + (y1 - y2) ** 2) ** 0.5, нужно посчитать растояние между городами.
### КОД:
```python
sites = {
    'Moscow': (550, 370),
    'London': (510, 510),
    'Paris': (480, 480),
}

distances = {}

for city1, x1 in sites.items():
    distances[city1] = {}
    for city2, x2 in sites.items():
        if city1 != city2:
            distance = (((x1[0] - x2[0]) ** 2) + ((x1[1] - x2[1]) ** 2)) ** 0.5
            distances[city1][city2] = distance

print(distances)
````

### РЕЗУЛЬТАТ:
![00.png](https://github.com/manabreako/python/blob/main/%D0%B1%D0%B5%D0%B1%D1%80%D0%B0/SCRENS/0.png)
## 01_circle
### Дан радиус круга: r= 42 и пи = 3.1415926.  Нужно найти пложнадь круга до точности в 4 знака после запятой. Точность мы указываем при помощи round().
### Так же даны 2 точки point_1 = (23, 34) и point_2 = (30, 30), надо определить, лежат они внутри круга или нет.
### КОД:
```python

radius = 42

pi = 3.1415926
S = radius**2 * pi
print(S)

point_1 = (23, 34)


M =(23**2 + 34**2)**0.5
if M < radius:
    print("True")
else:
    print("False")


point_2 = (30, 30)

N = (30**2 + 30**2) ** 0.5
if N < radius:
    print("True")
else:
    print("False")
```
### РЕЗУЛЬТАТ:
![01.png](https://github.com/manabreako/python/blob/main/%D0%B1%D0%B5%D0%B1%D1%80%D0%B0/SCRENS/1.png)
## 02_operation
### Надо между числа '1 2 3 4 5' раставить знаки операций так, что бы получился ответ 25.
### КОД:
```python
a = ((1*2)+3+(4*5))
print(a)
```
### РЕЗУЛЬТАТ:
![02.png](https://github.com/manabreako/python/blob/main/%D0%B1%D0%B5%D0%B1%D1%80%D0%B0/SCRENS/2%E2%81%842.png)
## 03_favorite_movies
### Надо при помощи индексации вывести на консоль фильмы из списка:
### my_favorite_movies = 'Терминатор, Пятый элемент, Аватар, Чужие, Назад в будущее' 
### в порядке - первый фильм, последний, второй, второй  с конца
### КОД:
```python
my_favorite_movies = 'Терминатор, Пятый элемент, Аватар, Чужие, Назад в будущее'

print(my_favorite_movies[0:10])
print(my_favorite_movies[42:57])
print(my_favorite_movies[12:25])
print(my_favorite_movies[-22:-17])

```
### РЕЗУЛЬТАТ:
![03.png](https://github.com/manabreako/python/blob/main/%D0%B1%D0%B5%D0%B1%D1%80%D0%B0/SCRENS/Screenshot_20250220_142009.png)
## 04_my_family
### Создаём список my_family = [] состоящий минимум из трёх элементов.
### При помощи данного списка заполняем список my_family_height = [] и добавляе рост каждому элементу списка
### Выводим на консоль отдельно рост отца, и общий рост всех членов семьи.
### КОД:
```python

my_family = ['я', 'отец', 'мама', 'сестра']

my_family_height = [
    ['я', 143], # мой рост
    ['отец', 197], # рост отца
    ['мама', 179], # рост мамы
    ['сестра', 110], # рост сестры
]

father_height = next(height for name, height in my_family_height if name == 'отец')
print(f'Рост отца - {father_height} см')

all_height = sum(height for name, height in my_family_height)
print(f'Общий рост - {all_height} см')

```
### РЕЗУЛЬТАТ:
![04.png](https://github.com/manabreako/python/blob/main/%D0%B1%D0%B5%D0%B1%D1%80%D0%B0/SCRENS/4.png)
## 05_zoo
### Дан список животных zoo = ['lion', 'kangaroo', 'elephant', 'monkey', ].
### Нужно посадить между 'lion' и 'kangaroo' 'bear', и вывести список.
###  Дальше надо обьединить список birds = ['rooster', 'ostrich', 'lark', ] с списком zoo и вывести в консоль.
### Убираем слона и снова выводим список в консоль.
### Выводим на консоль клетки, в который сидит 'lion' и 'lark'.
### КОД:
```python
zoo = ['lion', 'kangaroo', 'elephant', 'monkey', ]

zoo.insert(1, 'bear')
print('Список животных после добавления медведя: ', zoo)


birds = ['rooster', 'ostrich', 'lark', ]


zoo.extend(birds)
print('Список животных после добавления птиц: ', zoo)


zoo.remove('elephant')
print('Список животных без слона: ', zoo)


lion_pos = zoo.index('lion') + 1
lark_pos = zoo.index('lark') + 1
print(f'Лев сидит в клетке №{lion_pos}, а жаворонок в клетке №{lark_pos}')
```
### РЕЗУЛЬТАТ:
![05.png](https://github.com/manabreako/python/blob/main/%D0%B1%D0%B5%D0%B1%D1%80%D0%B0/SCRENS/5.png)
## 06_song_list
### Дан список песен Depeche Mode со временем звучания с точностью до долей минут.
### Нужно вывести на консоль общее время звучания трех песен: 'Halo', 'Enjoy the Silence' и 'Clean'
### в формате: Три песни звучат ХХХ.XX минут
### Так же дан словарь песен Depeche Mode, надо вывести общее время звучания трех песен:
### 'Sweetest Perfection', 'Policy of Truth' и 'Blue Dress' в формате:  А другие три песни звучат ХХХ минут.
### КОД:
```python
violator_songs_list = [
    ['World in My Eyes', 4.86],
    ['Sweetest Perfection', 4.43],
    ['Personal Jesus', 4.56],
    ['Halo', 4.9],
    ['Waiting for the Night', 6.07],
    ['Enjoy the Silence', 4.20],
    ['Policy of Truth', 4.76],
    ['Blue Dress', 4.29],
    ['Clean', 5.83],
]



time = round(violator_songs_list[3][1]+violator_songs_list[5][1]+violator_songs_list[-1][1], 2)
print('Три песни звучат: ', time, ' минуты')


violator_songs_dict = {
    'World in My Eyes': 4.76,
    'Sweetest Perfection': 4.43,
    'Personal Jesus': 4.56,
    'Halo': 4.30,
    'Waiting for the Night': 6.07,
    'Enjoy the Silence': 4.6,
    'Policy of Truth': 4.88,
    'Blue Dress': 4.18,

    'Clean': 5.68,
}



secondtime = round(violator_songs_dict['Sweetest Perfection'] + violator_songs_dict['Policy of Truth'] + violator_songs_dict['Blue Dress'])
print('А другие три песни звучат: ', secondtime, 'минут')
```
### РЕЗУЛЬТАТ:
![06.png](https://github.com/manabreako/python/blob/main/%D0%B1%D0%B5%D0%B1%D1%80%D0%B0/SCRENS/6.png)
## 07_secret
### Есть зашифрованное сообщение
### secret_message = [
###    'квевтфпп6щ3стмзалтнмаршгб5длгуча',
###    'дьсеы6лц2бане4т64ь4б3ущея6втщл6б',
###    'т3пплвце1н3и2кд4лы12чф1ап3бкычаь',
###    'ьд5фму3ежородт9г686буиимыкучшсал',
###    'бсц59мегщ2лятьаьгенедыв9фк9ехб1а',
### ]
### с помощью индексации расшифровываем и при поддержке ключей расшифровываем сообщение
+ ### Ключи к расшифровке:
1. ###   первое слово - 4-я буква
2. ###   второе слово - буквы с 10 по 13, включительно
3. ###   третье слово - буквы с 6 по 15, включительно, через одну
4. ###   четвертое слово - буквы с 8 по 13, включительно, в обратном порядке
5. ###   пятое слово - буквы с 17 по 21, включительно, в обратном порядке
### КОД:
```python

secret_message = [
    'квевтфпп6щ3стмзалтнмаршгб5длгуча',
    'дьсеы6лц2бане4т64ь4б3ущея6втщл6б',
    'т3пплвце1н3и2кд4лы12чф1ап3бкычаь',
    'ьд5фму3ежородт9г686буиимыкучшсал',
    'бсц59мегщ2лятьаьгенедыв9фк9ехб1а',
]


a = secret_message[0][3]
b = secret_message[1][9:13]
c = secret_message[2][5:14:2]
d = secret_message[3][7:13][::-1]
e = secret_message[4][16:21][::-1]
print(a, b, c, d, e)
```
### РЕЗУЛЬТАТ:
![07.png](https://github.com/manabreako/python/blob/main/%D0%B1%D0%B5%D0%B1%D1%80%D0%B0/SCRENS/7.png)
## 08_garden
### Даны кортежи garden = ('ромашка', 'роза', 'одуванчик', 'ромашка', 'гладиолус', 'подсолнух', 'роза', )
### и meadow = ('клевер', 'одуванчик', 'ромашка', 'клевер', 'мак', 'одуванчик', 'ромашка', )
- ### Задачи:
1. #### При помощи set() переделываемм их в списки.
2. #### выводим на консоль все виды цветов.
3. #### выводим на консоль те, которые растут и там и там.
4. #### выводим на консоль те, которые растут в саду, но не растут на лугу.
5. #### выводим на консоль те, которые растут на лугу, но не растут в саду.
### КОД:
```python
garden = ('ромашка', 'роза', 'одуванчик', 'ромашка', 'гладиолус', 'подсолнух', 'роза', )

meadow = ('клевер', 'одуванчик', 'ромашка', 'клевер', 'мак', 'одуванчик', 'ромашка', )


garden_set = set(garden)
meadow_set = set(meadow)


print ('Все виды цветов: ', 'Сад - ', str(garden_set), 'Луг - ', str(meadow_set))


together=garden_set&meadow_set
print('Растут и там и там: ', together)


print('Растут в саду, но не растут на лугу: ', garden_set-meadow_set)


print('Растут на лугу, но не растут в саду: ', meadow_set-garden_set)
```
### РЕЗУЛЬТАТ:
![08.png](https://github.com/manabreako/python/blob/main/%D0%B1%D0%B5%D0%B1%D1%80%D0%B0/SCRENS/8.png)
## 09_shoping
### Дан словарь магазинов shops в который входят ашан, пятёрочка и магнит, а так же сладости.
### Надо создать словарь цен, состоящий из двух магазинов с минимальными ценами.
### КОД:
```python
shops = {
    'ашан':
        [
            {'name': 'печенье', 'price': 10.99},
            {'name': 'конфеты', 'price': 34.99},
            {'name': 'карамель', 'price': 45.99},
            {'name': 'пирожное', 'price': 67.99}
        ],
    'пятерочка':
        [
            {'name': 'печенье', 'price': 9.99},
            {'name': 'конфеты', 'price': 32.99},
            {'name': 'карамель', 'price': 46.99},
            {'name': 'пирожное', 'price': 59.99}
        ],
    'магнит':
        [
            {'name': 'печенье', 'price': 11.99},
            {'name': 'конфеты', 'price': 30.99},
            {'name': 'карамель', 'price': 41.99},
            {'name': 'пирожное', 'price': 62.99}
        ],
}
sweets = {
    'печенье': [
        {'shop': 'ашан', 'price': 10.99},
        {'shop': 'пятерочка', 'price': 9.99}
    ],
    'конфеты': [
        {'shop': 'пятерочка', 'price': 32.99},
        {'shop': 'магнит', 'price': 30.99}
    ],
    'карамель': [
        {'shop': 'ашан', 'price': 45.99},
        {'shop': 'магнит', 'price': 41.99}
    ],
    'пирожное': [
        {'shop': 'пятерочка', 'price': 59.99},
        {'shop': 'магнит', 'price': 62.99}
    ],
}
print(sweets.setdefault('печенье'))
print(sweets.setdefault('конфеты'))
print(sweets.setdefault('карамель'))
print(sweets.setdefault('пирожное'))
```
### РЕЗУЛЬТАТ:
![09.png](https://github.com/manabreako/python/blob/main/%D0%B1%D0%B5%D0%B1%D1%80%D0%B0/SCRENS/9.png)
## 10_store
### Есть словарь кодов товаров - goods = {} и словарь списков количества товара на складе store = {}
### Рассчитать на какую сумму лежит каждого товара на складе
### КОД:
```python
goods = {
    'Лампа': '12345',
    'Стол': '23456',
    'Диван': '34567',
    'Стул': '45678',
}


store = {
    '12345': [
        {'quantity': 27, 'price': 42},
    ],
    '23456': [
        {'quantity': 22, 'price': 510},
        {'quantity': 32, 'price': 520},
    ],
    '34567': [
        {'quantity': 2, 'price': 1200},
        {'quantity': 1, 'price': 1150},
    ],
    '45678': [
        {'quantity': 50, 'price': 100},
        {'quantity': 12, 'price': 95},
        {'quantity': 43, 'price': 97},
    ],
}


lamps_cost = store[goods['Лампа']][0]['quantity'] * store[goods['Лампа']][0]['price']
lamp_code = goods['Лампа']
lamps_item = store[lamp_code][0]
lamps_quantity = lamps_item['quantity']
lamps_price = lamps_item['price']
lamps_cost = lamps_quantity * lamps_price
print('Лампа -', lamps_quantity, 'шт, стоимость', lamps_cost, 'руб')


table_cost1=0
table_code = goods['Стол']
table_cost=(store[goods['Стол']][0]['quantity']*store[goods['Стол']][0]['price'])+(store[goods['Стол']][1]['quantity']*store[goods['Стол']][1]['price'])
table_quantity = (store[goods['Стол']][0]['quantity'])+(store[goods['Стол']][1]['quantity'])
print('Стол -', table_quantity, 'шт, стоимость', table_cost, 'руб')

chear_cost = (store[goods['Стул']][0]['quantity']*store[goods['Стул']][0]['price'])+(store[goods['Стул']][1]['quantity']*store[goods['Стул']][1]['price'])+(store[goods['Стул']][2]['quantity']*store[goods['Стул']][2]['price'])
chear_code = goods['Стул']
chear_item = (store[goods['Стул']][0]['quantity'])+(store[goods['Стул']][1]['quantity'])+(store[goods['Стул']][2]['quantity'])
print('Стул -', chear_item, 'шт, стоимость', chear_cost, 'руб')

print('Диван -', (store[goods['Диван']][0]['quantity'])+(store[goods['Диван']][1]['quantity']), 'шт, стоимость', (store[goods['Диван']][0]['quantity']*store[goods['Диван']][0]['price'])+store[goods['Диван']][1]['quantity']*store[goods['Диван']][1]['price'], 'руб')


```
### РЕЗУЛЬТАТ:
![10.png](https://github.com/manabreako/python/blob/main/%D0%B1%D0%B5%D0%B1%D1%80%D0%B0/SCRENS/10.png)


## Шпаргалка по GIT

#### git clone "ссылка" - просим Git создать копию репозитория, который находится по ссылке
#### git add falename.pg - это команда в системе контроля версий Git, которая позволяет добавить изменения в индекс. После выполнения этой команды, Git отслеживает и фиксирует изменения для последующего коммита.
#### git status - отображает состояние рабочего каталога и раздела проиндексированных файлов. С ее помощью можно проверить индексацию изменений и увидеть файлы, которые не отслеживаются Git. Информация об истории коммитов проекта не отображается при выводе данных о состоянии.
#### git diff - Показывает различия по внесённым изменениям в ещё не проиндексированных файлах
#### git commit - добавление файлов в репозиторий 
#### git restore - отмена изменений
#### git push - отправка изменений в удалённый репозиторий


