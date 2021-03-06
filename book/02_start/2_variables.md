##Переменные

Переменные в Python:
* не требуют объявления типа переменной (Python - язык с динамической типизацией)
* являются ссылками на область памяти

Правила именования переменных:
* имя переменной может состоять только из букв, цифр и знака подчеркивания
* имя не может начинаться с цифры
* имя не может содержать специальных символов @, $, %

Создавать переменные в Python очень просто:
```python
In [1]: a = 3

In [2]: b = 'Hello'

In [3]: c, d = 9, 'Test'

In [4]: print(a,b,c,d)
3 Hello 9 Test
```

Обратите внимание, что в Python не нужно указывать, что a это число, а b это строка.

Переменные являются ссылками на область памяти. Это легко продемонстрировать с помощью функции ```id()```, которая показывает идентификатор объекта:
```python
In [5]: a = b = c = 33

In [6]: id(a)
Out[6]: 31671480

In [7]: id(b)
Out[7]: 31671480

In [8]: id(c)
Out[8]: 31671480
```

В этом примере видно, что все три имени ссылаются на один и тот же идентификатор.
То есть, это один и тот же объект, на который указывают три ссылки a, b и c.

С числами у Python есть ещё одна особенность, которая может немного сбить.
Числа от -5 до 256 заранее созданы и хранятся в массиве (списке).
Поэтому при создании числа из этого диапазона фактически создается ссылка на число в созданном массиве.

> Эта особенность характерна именно для реализации CPython, которая рассматривается в курсе.

Это можно проверить таким образом:
```python
In [9]: a = 3

In [10]: b = 3

In [11]: id(a)
Out[11]: 4400936168

In [12]: id(b)
Out[12]: 4400936168

In [13]: id(3)
Out[13]: 4400936168
```

Обратите внимание, что у ```a```, ```b``` и числа ```3``` одинаковые идентификаторы.
Все они просто являются ссылками на существующее число в списке.

Но если сделать то же самое с числом больше 256:
```python
In [14]: a = 500

In [15]: b = 500

In [16]: id(a)
Out[16]: 140239990503056

In [17]: id(b)
Out[17]: 140239990503032

In [18]: id(500)
Out[18]: 140239990502960
```

Идентификаторы у всех разные.

При этом, если сделать присваивание такого вида:
```python
In [19]: a = b = c = 500
```

Идентификаторы будут у всех одинаковые:
```python
In [20]: id(a)
Out[20]: 140239990503080

In [21]: id(b)
Out[21]: 140239990503080

In [22]: id(c)
Out[22]: 140239990503080
```

Так как в таком варианте a, b и c просто ссылаются на один и тот же объект.

### Имена переменных

Имена переменных не должны пересекаться с операторами и названиями модулей или других зарезервированных значений.


В Python есть рекомендации по именованию функций, классов и переменных:
* имена переменных обычно пишутся полностью большими или маленькими буквами
  * DB_NAME
  * db_name
* имена функций задаются маленькими буквами, с подчеркиваниями между словами
  * get_names
* имена классов задаются словами с заглавными буквами, без пробелов
  * CiscoSwitch

