# Team mai54

## Документация по языку ZYX
### Реализованные функции языка
* [x]  Именованные переменные (`let`)
* [x]  Рекурсия
* [x]  Функции
* [x]  Замыкания

### Типы
Поддерживается 2 типа данных - целое число и строка.
###  Арифметические операции
Поддерживается 4 арифметические операции: `PLUS`, `MINUS`, `MULTIPLY`, `DIVIDE`.
#### Пример:
```
[PLUS "String1" "String2"]
[PLUS 10 5]
[MINUS 10 5]
[MULTIPLY 10 10]
[DIVIDE 33 3]
[DIVIDE [MULTIPLY 500 2] [MINUS -20 -10]]
```
#### Результат:
```
String1String2
15
5
100
11
-100
```
###  Операторы сравнения
Поддерживается 5 операторов сравнения: `EQ`, `MORE`, `LESS`, `MOREEQ`, `LESSEQ`. Если верно - выводится `1`, неверно - `0`.
#### Пример:
```
[MORE 9 9]
[MOREEQ 9 9]
[EQ "str1" "str2"]
[LESSEQ "str1" "str2"]
```
#### Результат:
```
0
1
0
1
```
### Условный оператор
Синтаксис: `[IF [[*condition*] [*statement1*]] *statement2*]`
#### Пример:
```
[IF [[EQ 10 10] ["Equal!"]] "Not equal!"]
[IF [[EQ 1 10] ["Equal!"]] "Not equal!"]
```
#### Результат:
```
Equal!
Not equal!
```
### Именованные переменные
Объявляются с помощью `LET`
#### Пример:
```
[LET [[x 6]] [x]]
[LET [[x 1] [y 2]] [PLUS x y]]
[LET [[x "1"] [y "2"]] [PLUS x y]]
```
#### Результат:
```
6
3
12
```
###  Лямбда-выражения
#### Пример:
```
[[LAMBDA [val1 val2 val3 val4] [PLUS [MULTIPLY val1 val2] [MULTIPLY val3 val4]]] 2 4 6 8]

```
#### Результат:
```
56
```
###  Функции
Объявление функции - `LET`, вызов функции - `CALL`.
#### Пример:
```
[LET [[myPow [LAMBDA [a] [MULTIPLY a a]]]] [CALL [myPow 3]]]
[LET [[myABS [LAMBDA [a] [IF [[MOREEQ a 0] a] [MINUS 0 a]]]]] [CALL [myABS -3]]]
```
#### Результат:
```
9
3
```
###  Рекурсия
Объявление рекурсивной функции - `LETREC`.
#### Пример:
```
[LETREC [[fact [LAMBDA [x] [IF [[LESSEQ x 1] 1] [MULTIPLY x [CALL [fact [MINUS x 1]]]]]]]] [CALL [fact 5]]]
```
#### Результат:
```
120
```
###  Замыкания
#### Пример:
```
[LET [[myMultiply [LAMBDA [n] [LAMBDA [x] [MULTIPLY n x]]]]] [CALL [myMultiply 3 5]]]

```
#### Результат:
```
15
```
### Примеры программ
[Репозиторий](https://github.com/MAILabs-Edu-2024/fp-compiler-lab-mai54/tree/main/samples), содержащий примеры программ.

## Team mai54 

| ФИО                               | Роль в проекте                                                                |
| ---                               | ---                                                                           |
|  Старцев Иван Романович           | Разработка парсера, написание  документации                                   | 
|  Румынина Екатерина Александровна | Разработка интерпретатора, написание  документации                            |
|  Гришин Павел Федорович           | Разработка интерпретатора, написание  документации                            |
