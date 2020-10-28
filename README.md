# Отчет о лабораторных работах 

# студент группы ИДБ-17-06 Сахабетдинов М.Х.

## Лабораторная 1

Пользователь экспортирует Excel файл в CSV файл

![idef0](https://github.com/MartyStev/SakhabetdionovMarat.github.io/blob/master/lab1/01_A0.png?raw=true)

Пользователь должен экспортировать данные в CSV файл в соответствии с требованиями формата данных, пользуясь исходными данными (в качестве которых Excel файл) и ПО MS Excel

Диаграмма классов

![диаграмма классов](https://github.com/MartyStev/SakhabetdionovMarat.github.io/blob/master/lab1/uml-class.png?raw=true)

Диаграмма прецедентов

![Диаграмма прецедентов](https://github.com/MartyStev/SakhabetdionovMarat.github.io/blob/master/lab1/uml-prec.png?raw=true)

## Лабораторная 2

Диаграмма IDEF0:
Контекстная:

![idef0](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/lab2/01_A0а.png)

На диаграмме изображен процесс работы гоночной команды
Средний уровень:

![2а0](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/lab2/02_A0а.png)

A1 Менеджер получает на вход расписание этапов гоночной серии и результаты пройденных этапов. На выходе резльтаты за серию (Предпологаемое чемпионство).

А2 Снабженец получает расписание гонок и наряд заказ на необходимые запчасти для закупки. Исходя из графика и заказа занимается снабжением, на выходе предоставляя запчасти.

А3 Механик получает расписание гонок, запчасти и технические проблемы (по результатам пройденных заездов), на основе которых выполняет сборку автомобиля, на выходе предоставляя готовый к заездам автомобиль.

А4 Пилот (Гонщик) получает расписание предстоящих гонок, автомобиль, на основе которых проходят заезды и на выходе определяя возникшие технические проблемы а так же предоставляя резльтаты заездов.


#DFD-диаграмма (блок:Снабдить):

![3а0](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/lab2/03_A2а.png)

Снабженец получает наряд заказ и заносит их в базу данных, определяя на основе расписаниях их необходимость в данный момент.

Диаграмма прецедентов:

![Диаграмма прецедентов](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/lab2/ump-proc.png?raw=true)

## Лабораторная 3
Диаграмма последовательности


![Диаграмма последовательности](http://www.plantuml.com/plantuml/png/ZP9FRXCn5CRNzIcixdk1Ia6b78ArCsF1A1uxydX0226L2bIa8bM2HJSW_fnW28n86vfSuVb6V2ysOZIQHJTEulVztlVvlPmqGVdGraOqYyekbLUrL4LmNhuK1wUgM3pnhhNb8sTmzVXf5RGuUEYzUvvkJWqa43fVQZ-yUYLK6vnjwxdsGgIEX_I9-lYMEhgZDTqUIjN8ja6zL47DLQEX-4fTV4qxMkDCkbxIJzhYwpOZvTohGW-XxzoMnV62Ue2t2Tl5Cq0_Q4Cz_OcN6LvwDpUw5jg6Ahm0VGsZ7KWOntDQxsNQYiBPu9tXJCnpX7Y-BwA2gZ6w29Mp3HGThO1keO8Vp3VnVLOQ8VY9ykX1pdqiwGldGaoecOfdU26kklY6nqATICh4vBXZZA7VyFq5x8BdMprJGG-U9sQpZD2AUdoYyG2HivaGnhcbaF8_nPRQmkipT1kUPveaiC68UhfXwfyf2Fp4AOz6YJ6u-0xokubzx7tri8UsPKhz8LxI3ieDm0pVF_brrY5iJeLAuL0QBnfb57BTeFunxODMyB-HKqiTFfkXrCACD_MDzyHil4hnfvfTZIQ0FZo2qQlGcVy_nz8jidvwrHZA2UYsDdy1)


ER-диаграмма

![ER-Диаграмма](http://www.plantuml.com/plantuml/png/JL4zJiCm69thKrWPaNe3XjAoS09cavWagcD7jYi6G6eZVf2Oa91WO80RU02HLhIzmkSRyHadA8kbx_qylITFZ6NQBYf1pBoKDTEiegbWnj1BCfgoT9vhjP3PJ0cbwMbHMav6HrghYuXC1KfGg7J6zH2w9YJ6p9IqMeaJUQueCpI1LzZw6zZv9Vo0ytVGmWwsY3t2ci8UYGQ1JTBxQwwDaj7w3bzeGhblaewMhEAHV047dvXu3wudMTvn7nZS-bK8fl2DmdsG-PLlC77To-j2oSxmXkmIDk3eNyi7Q4F3_rB7pB8eV08N0YayWuip_2tAXgiFhyRZw23XZNUSHRfr1uY49SERvSCpbYEaA3DEArwT8HEFjDIfu3rX2vKPCk4omp_z1G00)

Ремонт является записью в БД, которая относится к информационным потокам, и состоит из: Задача, Список запчастей, Марка машины.
