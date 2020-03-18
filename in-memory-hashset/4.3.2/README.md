## Задача 2. База организаций

### Описание
Вы разрабатываете государственную систему учета организаций. Организация представлена следующими атрибутами – "название", "город", "адрес", "ИНН", "КПП", "ОГРН".
Ключом уникальности организации является сочетание “ИНН”+”КПП”+”ОГРН”. Структура данных, куда сохраняются организации, должна отбрасывать ввод одной и той же организации 2 раза.
Ввод пустой строки вместо организации завершает программу и выводит список организаций.

### Функционал программы
1. Ввод организаций: название, город, адрес, ИНН, КПП, ОГРН.
2. Вывод списка организаций.

### Пример
```
Введите название организации в следующем формате:
"Название, город, адрес, ИНН, КПП, ОГРН"
ООО Нетология, Москва, Ленина 5, 10123123, 12311121, 1117746358608 <enter>
...
<enter>
Список организаций:
  1. ООО Нетология, Москва, Ленина 5, 10123123, 12311121, 1117746358608
  2. ...
```

### Реализация
1. Создайте класс `Organization` с полями `Name`, `City`, `Address`, `INN`, `KPP`, `OGRN`. Тип всех полей – `String`.
2. Переопределите методы `hashcode` и `equals` для класса `Organization` так, чтобы нельзя было сохранить две организации, у которых все три поля "ИНН", "КПП", "ОГРН" были бы одинаковыми.
3. Продемонстрируйте добавление объектов класса в HashSet, ошибку при добавлении организаций с тремя одинаковыми параметрами, возможность существования нескольких организаций с одинаковым названием, городом и адресом.