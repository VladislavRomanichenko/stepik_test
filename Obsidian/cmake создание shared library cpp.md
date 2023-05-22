---
Тип: Задача
Описание: -
Исполнители: 
Проект: ВнедрениеЗнаний

Дисциплина: Программирование
Tags: Задачи
regex-to-search: "((.*)[Cc]make(.*))|((.*)[Ll]ibrar(.*))" # "что-то" regex
regex-to-be-found: "((.*)[Cc]make(.*))|((.*)[Ll]ibrar(.*))" # "что-то" regex

День: 08 # Не трогать!
Месяц: 12 # Не трогать!
Год: 2022 # Не трогать!
Дата_создания: Thursday 8th December 2022 11:41:04

день_завершения: 8
месяц_завершения: 12
год_завершения: 2022
дата_завершения: "2022-12-08"

Выполнено: нет
Результат: 
---

```dataview
TABLE день_завершения as "День истечения", месяц_завершения as "Месяц истечения", Проект, Выполнено, Результат, Количество_выходящих_задач as "Количество выходящих задач"
WHERE Дата_создания = this.Дата_создания
limit 1
```
# [[cmake создание shared library cpp]]

- Получение источников и ссылок
	- [x] Получение одной ссылки
	- [x] Получение ссылок на разные источники
- Конспектирование
	- [x] Достаточное для использования конспектирование
	- [ ] Полное конспектирование
- Создание справок
	- [x] Справки практического применения
	- [ ] Список терминов
	- [ ] Определение терминов из списка терминов
	- [ ] Список связанных тем(если нет внутри текста)
- [ ] Внедрение в практику

%%
## Результат:



## Следующая задача:

==#Входящие ==
%%

**Содержание потом вырезается, все содержимое конспекта удаляется и содержание вставляется по шаблону входящего конспекта.**



# Содержание 
> [!tldr]+ Алгоритм - Практическая справка
> Команды для самого проекта CMake здесь не учтены.
> 1. find_paсkage(\<dependecies_pkg\> REQUIRED) - ищем зависимости нашей либы
> 2. add_library(\<library_name\> STATIC|SHARED|MODULE source_files header_files) - создаем [[cmake target - что это|target]] библиотеки
> 3. target_link_libraries(\<library_name\> \<dependencies_pkg\>) - привязываем библиотеки, от которых зависит наша библиотека
> 4. target_include_directories(\<library_name\>
> PUBLIC|PRIVATE|PROTECTED(???)
> \$\<BUILD_INTERFACE:\${CMAKE_CURRENT_SOURCE_DIR}/include\>
> \$\<INSTALL_INTERFACE:include\>) - указываем путь на интерфейс(API - header-файлы) для других target, которые будут использовать нашу библиотеку
> 5. . . . создаем другие target и executable . . . 
> 6. install(TARGETS \<library_name\>
> 		ARCHIVE DESTINATION ${COLCON_PACKAGE_LIB_DESTINATION}
> 		LIBRARY DESTINATION ${COLCON_PACKAGE_LIB_DESTINATION}
> 		RUNTIME DESTINATION ${COLCON_GLOBAL_BIN_DESTINATION}) - без этого шага по крайней мере в [[Работа с ROS2|ROS2]] нод не видел header-файлы нашей библиотеки.

#Входящие 

%%
> [!example]- Список терминов
> - [ ] Пример
%%

> [!question]- Соурслист
> 1. https://stackoverflow.com/questions/17511496/how-to-create-a-shared-library-with-cmake
> 2. catkin http://docs.ros.org/en/jade/api/catkin/html/howto/format2/building_libraries.html#installing

%%
## Приложения
%%

## Связано:

```dataview
LIST 
FROM !outgoing([[]])
WHERE regexmatch(this.regex-to-search,regex-to-be-found) or regexmatch(this.regex-to-search, file.name) or regexmatch(this.ключи,regex-to-be-found) or regexmatch(regex-to-search, this.regex-to-be-found)
```

---
#ВнедрениеЗнаний #Программирование/cmake 