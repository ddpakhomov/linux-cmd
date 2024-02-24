Примеры использования команды **awk**
-
### Базовый синтаксис
---

Вывод всего содержимого <br>
`awk '{print $0}' information.txt` <br>
Добавить нумерацию строк <br>
`awk '{print NR,$0}' information.txt`
Вывод конкретного поля <br>
`awk '{print $1}' information.txt` <br>
Вывод 1 и 4 столбца <br>
`awk '{print $1,$4}' information.txt | head -n4` <br>
`awk '{print $1,$4}' information.txt | head -4` <br>
`awk '{print $1,$4}' information.txt | head -1` <br>
### Вывод строк с заданным шаблоном
---
Вывод строк, которые начинаются с заданной буквы __D__<br>
`awk '/^D/' information.txt` <br>

Завершается заданным шаблоном __0__<br>
`awk '/0$/' information.txt` <br>
Выбрать строки, которые __НЕ__ оканчиваются на __0__ <br>
`awk '! /0$/' information.txt` <br>
Вывести строки, которые содержат __io__ <br>
`awk '/io/{print $0}' information.txt` <br>
можно сократить, вывод строк содержащих __Eng__ <br>
`awk '/Eng/' information.txt` <br>
Вывести 1 и 2 поле/столбец тех строк, которые содержат __Eng__ <br>
`awk '/Eng/{print $1,$2}' information.txt` <br>
> для вывод последнего поля можно использовать `$NF` <br>
> экранирующий символ `\` <br>

Случай где необходимо использовать символ экранирования для шаблона `N/A` <br>
`awk '/N\/A$/' information.txt` <br>
`awk '/N\/A/' information.txt` <br>
Вывести строки, в которых значение поля 3 меньше 40 <br>
`awk '$3 < 40 {print $0}' information.txt` <br>
