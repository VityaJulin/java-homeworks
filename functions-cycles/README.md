Домашнее задание по лекции 1.2. Основы синтаксиса - функции и циклы
==
Вы продолжаете работу над разработкой менеджера задач для разработчиков ([примеры приложений](https://netology.ru/blog/5-todo)). Выполните задачи для реализации различных функций.

## Задача 1. Перевод времени
### Описание
Для работы менеджера задач нам нужно сравнивать разные по длительности задачи.

Вам нужно разработать часть фунциональности, отвечающую за перевод времени из одних единиц в другие. Например – на одну задачу нужно 2 дня, 4 часа и 10 минут, на вторую задачу нужно 3 дня, 4 часа и 15 минут. Хранить и использовать три переменные не удобно, поэтому для хранения времени обычно используют минимальную из используемых единиц. В нашем случае это минуты. Например задача занимает 1 день 2 часа 10 минут, а программа переводит и хранит это как 24*60*1+60*2+10=1570 минут. С одной переменной уже гораздо проще выполнять сравнение, сложение и вычитание.

Вам нужно написать программу, которая примет на ввод длительность задачи - 3 числа: число дней, минут и часов. Далее, вам нужно перевести введенное время в минуты. Потом запросить у пользователя в какую величину он хочет перевести результат: `дни`, `часы` или `минуты`, и вывести на экран длительность в соответствующем формате.

### Процесс реализации
1. Используя `Scanner scanner = new Scanner(System.in)` и `scanner.nexInt()` последовательно получить ввод трех чисел и созранить их в переменные `int days`, `int hours`, `int minutes` для дней, часов и минут соответственно. Перед каждым запросом на ввод нужно выводить сообщение (`System.out.println("...");`), чтобы пользователь понимал, что ему вводить.
2. Создать переменную `int totalTimeMinutes`, вычислить и сохранить туда полное время задачи в минутах.
3. Создать 2 функции `public float convertToDays(int totalTimeMinutes)`, `public float convertToHours(int totalTimeMinutes)`.
4. Получить на ввод единицу измерения времени для вывода: `дни`, `часы` или `минуты`, и сохранить в переменную `String convertTo`.
5. Используя `switch(convertTo)` вызвать необходимую функцию вывести длительность задачи в выбранном пользователем формате.

### Примеры
Пользователь вводит: 1, 5, 30, дни
Вывод: 1.23

Пользователь вводит: 0, 0, 120, часы
Вывод: 2.0


## Задача 2. Суммирование времени.
### Описание

Вы планируете задачи своей команды на неделю. При составлении задач для программиста необходимо следить за тем, чтобы его нагрузка не вышла за определенные рамки.

Для этого вам нужна программа, которая может вычислить суммарное время выполнения задач, общее количество которых заранее неизвестно. Пользователь будет поочередно вводить длительность задач в минутах. После ввода длительности последней задачи он введет `end`. После этого программа должна вывести суммарную длительность задач в минутах.

### Процесс реализации
0. Создать переменную, в которой будет храниться суммарная длительность задач и переменную `int totalTime`, в которой будут храниться вводимые пользователем значения `int inputString`.
1. Получить ввод длительности первой задачи.
2. Используя цикл `while` получить ввод длительности оставшихся задач. Для проверки на ввод `end` нужно использовать `inputString.equals("end")`, оператор `==` со строками не работает.
3. В цикле нужно привести введенную строку к числовому типу, и прибавить ее значение к переменной, в которой хранится суммарная длительность задач. Получить ввод нового значения в `inputString`.
4. После того как пользователь введет `end` и программа выйдет из цикла нужно вывесли на экран суммарную длительность задач.

Не забывайте выводит понятные пользователю приглашения на ввод и сообщения при выводе данных на экран.

### Примеры
Пользователь вводит: 60, 120, 360, end
Вывод: 540

## Задача 3. Калькулятор выплат по ипотеке.

Вы пишете кредитный калькулятор. Он должен рассчитывать сумму выплат по ипотеке за несколько лет.
Пользователь вводит сумму кредита, % по ипотеке, и срок займа.
Программа рассчитывает и выводит пользователю общую сумму, которую он заплатит банку.

Мы рассматриваем упрощенный случай когда банк начисляет проценты ежемесячно на всю оставшуюся сумму кредита. Платежи основной суммы кредита при этом одинаковые каждый месяц, но к ним прибавляется сумма процентов, начисленная на оставшуюся сумму за месяц. Например, кредит 6 млн на 120 месяцев под 8%: каждый месяц нужно платить 60000 плюс проценты. Проценты в первый месяц 54000 (6000000\*0.008), а значит за первый месяц придется заплатить 114000. За последний проценты 480 (оставшиеся 60000\*0.008), значит за послений месяц будет заплачено 60480.

### Процесс реализации
1. Получить ввод трех чисел: сумма кредита, длительность в месяцах и процентная ставка.
2. Созать переменную для хранения общей суммы выплат.
3. Используя цикл `for` выполнить рассчеты за каждый месяц: вычислить сумму начисленных процентов и прибавить ее к общей сумме выплат, прибавить ежемесячный платеж к сумме выплат, вычесть ежемесячный платеж из оставшейся суммы кредита. В конце, оставшаяся сумма кредита дложна стать равна 0.
4. Вывести вычисленную общую сумму выплат на экран.

Даже если вы знаете формулу, с помощью которой можно решить эту задачу без цикла, то не используйте её. :) Цель задания именно в тренировке использования цикла `for`.