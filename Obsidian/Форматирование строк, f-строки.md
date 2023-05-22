23.04.2023    19:11
Теги: #Python 
---
# ***Внутренние ссылки:***

---
# ***Внешние ссылки:***

---
# ***Заметка:***

# Форматирование строк

```python
age = 27
txt = 'My name is Timur, I am {}'.format(age)
print(txt)
```

Мы передаем необходимые параметры методу `format`, а Python форматирует указанную строку и помещает их в строку на место заполнителей `{}`. Мы можем создавать сколько угодно заполнителей в строке:

```python
age = 27
name = 'Timur'
profession = 'math teacher'
txt = 'My name is {}, I am {}, I work as a {}'.format(name, age, profession)
print(txt)
```

Для наглядности и гибкости форматирования мы можем использовать порядковый номер в заполнителе: `{0}, {1}, {2},...`. Такой номер определяет позицию параметра, переданного методу `format` (нумерация начинается с нуля):

```python
age = 27
name = 'Timur'
profession = 'math teacher'
txt = 'My name is {0}, I am {1}, I work as a {2}'.format(name, age, profession)
print(txt)
```

Параметр `name` встает в `{0}` заполнитель, параметр `age` встает в `{1}` заполнитель и т.д. Мы можем использовать одно и тоже число в нескольких заполнителях

```python
name = 'Timur'
txt = 'My name is {0}-{0}-{0}'.format(name)
print(txt)
```

Результатом выполнения такого кода будет:

```no-highlight
My name is Timur-Timur-Timur 
```

# f-строки

Метод `format` хорошо справляется с задачей форматирования строк, однако если параметров много, то код может показаться немного избыточным:

```python
first_name = 'Timur'
last_name = 'Guev'
age = 27
profession = 'math teacher'
affiliation = 'BeeGeek'
print('Hello, {0} {1}. You are {2}. You are a {3}. You were a member of {4}'.format(first_name, last_name, age, profession, affiliation))
```

В Python 3.6 появилась новая разновидность строк — так называемые f-строки. Если поставить перед строкой префикс f, в заполнители можно будет включить код, например имя переменной. Предыдущий код можно записать в виде:

```python
first_name = 'Timur'
last_name = 'Guev'
age = 27
profession = 'math teacher'
affiliation = 'BeeGeek'
print(f'Hello, {first_name} {last_name}. You are {age}. You are a {profession}. You were a member of {affiliation}')
```

На место заполнителя `{first_name}` встает значение переменной `first_name`, на место  заполнителя `{last_name}` встает значение переменной `last_name` и т.д.

# Примечания

**Примечание 1.** [Подробная документация](https://docs.python.org/3/library/string.html#custom-string-formatting) с форматированием строк.