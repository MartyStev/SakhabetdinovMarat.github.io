## Курсовой проект по дисциплине "Проектирование информационных систем"

## Сахабетдинов Марат, ИДБ-17-06

### 1. Определение требований к модели [✋](https://github.com/stankin/design-part-2/wiki/LR-1)

**Тема ВКР:** Разработка средств ETL-процесса для интеграции информационных систем

**Объект исследований:** предметно-ориентированные информационные базы данных.

**Предмет исследований:** процессы извлечения, преобразования, загрузки данных, при реализации ETL-процесса.

**Процессы верхнего уровня:** [✋](https://github.com/stankin/design-part-2/wiki/sem1)
* **А1** Сбор данных
* **А2** Профилирование данных
* **А3** Преобразоавние данных
* **А4** Выгрузка данных
* **А5** Оценка соответствия полученных данных

**Точка зрения:** Руководитель отдела

**Цель моделирования:** Определение автоматизируемых функций

### 2. Функциональное моделирование процессов (IDEF0) [✋](https://github.com/stankin/design-part-2/wiki/LR-1)

* A-0 (контекстная диаграмма)

![A-0](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/design-part-2/lab1-3/01_A0.png)

* Процессы A-0

![A0](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/design-part-2/lab1-3/02_A0.png)

* Декомпозиция А-1

![A0](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/design-part-2/lab1-3/03_A1.png)

* Декомпозиция А-2

![A0](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/design-part-2/lab1-3/05_A2.png)

* Декомпозиция А-3

![A0](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/design-part-2/lab1-3/09_A3.png)


### 3. Функциональное моделирование программных и информационных средств (DFD) [✋](https://github.com/stankin/design-part-2/wiki/LR-2)

**Конфигурация технических средств:** сервер,храненилища данных; сервер обработки данных

**Конфигурация программных средств:** двухуровневая

**Допустимые виды хранилищ и их размещение:** OLTP/OLAP БД

* A12 Автоматизация процесса А12

![A31](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/design-part-2/lab1-3/04_A12.png)

* A21 Автоматизация процесса А21

![A32](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/design-part-2/lab1-3/06_A21.png)

* A22 Автоматизация процесса А22

![A32](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/design-part-2/lab1-3/07_A22.png)

* A23 Автоматизация процесса А23

![A32](https://github.com/MartyStev/SakhabetdinovMarat.github.io/blob/master/design-part-2/lab1-3/08_A23.png)

### 4. Описание выбранного процесса [✋](https://github.com/stankin/design-part-2/wiki/LR-3) в формате прецедента (Use Case) [✋](https://github.com/stankin/design-part-2/wiki/LR-4)

Диаграмма UML Use Case
![p4](http://www.plantuml.com/plantuml/proxy?idx=0&src=https://raw.githubusercontent.com/<user/user.github.io/master/<path><file>)

**4.1 Идентификатор прецедента:** A2

**4.2 Название прецедента:** Трансформация данных

**4.3 Контекст:** Интеграция данных

**4.4 Участники (actors) и цели (goals):**

| Участник  | Категория  | Цель (goal) |
|---|---|---|
| Инженер данных | Основной  | Подключять источники данных, формировать ETL конфигурацию |
| Аналитик | Внешний  | Формирвать метрики, формулы агреграций |
| База данных (источник) | Инструмент| Хранение не обработнных данных |
| База данных (хранилище) | Инструмент| Хранение обработнных данных |
| ETL/ELT | Инструмент| Извлечение, преобразование, загрузка данных|

**4.5 Предусловия (pre-conditions):**

* Условие наличия потока управления: BI, Требования к данным.

* Условие наличия входного потока: Поток данных.

* Условие наличия потока исполнителя: Инженер, Аналитик.

* Условие наличия потока механизма: Работающая система (результаты выгрузки).

**4.6 Постусловия (post-conditions):**

* Выходной поток: Конфигурация ETL задач.

**4.7 Основной поток выполнения (main flow)**:

| Участник  | Действие (activity)  | Ожидаемый результат |
|---|---|---|
| Инженер | Проектирование сисетмы интеграции | Конфигурация ETL |
| Аналитик | Оперделение проверочных мерик, формул агрегаций | Параметры проверки данных |
| ETL | Извлечение | получение первичных данных |
| ETL | Трансформация | преобразование первичных данных |
| ETL | Загрузка | получеине аналитических данных |

**4.8 Исключения (exceptions):**

| Условие (риск) | Последствия | Реакция |
|---|---|---|
| Невозможность подключения к источнику данных| Недоступность данных | Выполнение повтороного подключения |
| Получение данных неверного формата | Получение ошибочных значений | Выполнить конвертацию данных |
| Изменение архитектры источника данных | Ошибка сопоставления данных | Нет |

**4.9 Альтернативы (alternates):**

| Участник  | Действие (activity)  | Ожидаемый результат |
|---|---|---|
| Аналитик | Новый источник данных | Дополнение системы интеграции новым источником |

**4.10 Временные параметры:**

* **Триггер (событие, стартующее прецедент):** <управляющий поток>

* **Номинальная частота повторения прецедента:** <n раз в смену/сутки/месяц/квартал/год...>

* **Продолжительность прецедента:** <n нормочасов>

### 5. Описание структуры объекта [✋](https://github.com/stankin/design-part-2/wiki/LR-3) в формате ERD (Class) [✋](https://github.com/stankin/design-part-2/wiki/LR-5)
* **Описываемый объект:** Интеграция данных
![](http://www.plantuml.com/plantuml/png/bOzFJi906CNNp2actNC35uY7S5tRYJHC6JDJua9Dy4ya94PZujBenWC0GfWKgLTutusSCccefWlSpNlpVk_BwvWirDambSpqay5PgCEKHp8qXb-mLZUC-gTQ3GVnaP9Ay-DUaWdMEjHQdNkdArt41PMEXQvRLyotu1K55dIBDMnbVJYvGKxti3lp3JCQOOeP2hgXCInonkhqmMMx_OTj-6-g-GNvN53tw8dZkon2ZZKzEcg9ZRTpZcUy1CqLxrXZkasEK61E4zWIM3bpWIcDWxqk5zlRSonfKjqDMDCEZ-ycqmE7nQf4dHZ_6tPVPMX3rtI7mhs_gYL-5PRxLldDdpHoSeKSDc2z91Oy5Uc9qCQBAD6H5DL7rbEnOHqnY8Uf_040)


### 6. Описание алгоритма [✋](https://github.com/stankin/design-part-2/wiki/LR-3) в формате UML (Sequence) [✋](https://github.com/stankin/design-part-2/wiki/LR-6)

* **Описываемые процессы и потоки данных:** А21 Валидация данных

* **Диаграмма UML Sequence:**
![p6](http://www.plantuml.com/plantuml/proxy?idx=0&src=https://raw.githubusercontent.com/<user/user.github.io/master/<path><file>)

### 7. Описание состава [✋](https://github.com/stankin/design-part-2/wiki/LR-3) в формате UML (Component) [✋](https://github.com/stankin/design-part-2/wiki/LR-7)

* **Описываемый объект:** <комплект поставки>

* **Диаграмма UML Component:**
![p7](http://www.plantuml.com/plantuml/proxy?idx=0&src=https://raw.githubusercontent.com/<user/user.github.io/master/<path><file>)

### 8. Демонстрация реализации (личная страница)

<ссылка или скриншоты>

### 9. Подготовка к интерпретации построенных моделей

**9.1 Используемые паттерны проектирования и разработки [✋](https://github.com/stankin/design-part-2/wiki/sem2):**

* **Процессная модель для сравнения:**

* **Используемые в разработке паттерны и фреймворки:**

**9.2 Используемые паттерны выявления проблем [✋](https://github.com/stankin/design-part-2/wiki/sem3):**
* Муда: <муда>
* Мура: <мура>
* Мури: <мури>

**9.3 Возможные антипаттерны [✋](https://github.com/stankin/design-part-2/wiki/sem4):**

| Категория  | Антипаттерн (риск) | Действие по избежанию |
|---|---|---|
| Разработка | <антипаттерн> | <действие> |
| Архитектура | <антипаттерн> | <действие> |
| Организация | <антипаттерн> | <действие> |
| Среда | <антипаттерн> | <действие> |

### 10. Интерпретация построенных моделей

**10.1 Определение числовых показателей для поставленной цели моделирования:**

**10.2 Определение числовых показателей для цели потенциального проекта автоматизации: [✋](https://github.com/stankin/design-1/wiki/interpret_process)**

**10.3 Расчет потенциального эффекта от автоматизации:**

**10.4 Определение числовых показателей и расчет трудозатрат на разработку программных средств:**

**ВЫВОДЫ**

