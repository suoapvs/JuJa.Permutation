[![JuJa](logo-juja.png)](https://juja.com.ua)

## Задача #1

Разработайте алгоритм для вывода всех возможных перестановок
символов в строке

#### Строка с данными: algorithm

Ответ прислать в виде кода, который выдаст все возможные варианты
перестановок строки с данными.


## Решение

Идея такова: 
Для получения всех возможных перестановок переданной строки можно 
перебрать все варианты перестановок массива символов этой строки. 
Для перебора уникальных перестановок массива символов можно
используется итератор массива индексов уникальных символов строки.

Тогда, генерируем массив индексов -> с массива символов выбираем 
те символы, индексы которых мы получили -> создаем строковое 
представление созданного массива символов. И так далее...

Для получение всех перестановок массива индексов, его нужно 
отсортировать от восходящего к нисходящему или наоборот. 
Каждая итерация сортировки — это наша новая перестановка 
массива индексов.

Также решена проблема с повторениями символов в строке,
из-за чего возникают повторение перестановок
Например:

|  Строка  | Перестановки |
|:--------:|:-------------|
|  "aaa"   | "aaa", ~~"aaa"~~, ~~"aaa"~~ |
|  "aab"   | "aab", "aba", "baa", ~~"aab"~~, ~~"aba"~~, ~~"baa"~~ |
|  "abc"   | "abc", "acb", "bac", "bca", "cab", "cba" |

Среднее время поиска всех перестановок: **~30 мс** (1000 итераций).
