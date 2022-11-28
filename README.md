# Проект «Сшивка»

Генетический алгоритм формирует схему процесса из функциональных блоков,  заданных в файле [in_schem.txt](in_schem.txt "in_schem.txt").  

### Формат файла


*Имя функции<br />
-входная переменная 1, 2, 3<br />
-выходная переменная 1, 2, 3<br />
-цена (если нет строки = 0)*

Функции разделены минимум одной строкой.<br />
Обязательная функция:

*Target<br />
-Конечные цели<br />
-Имеющиеся ресурсы*

Функции задаются согласно концепции «Семантический ТРИЗ», т.е. входные и выходные параметры – [веполи](https://dic.academic.ru/dic.nsf/ruwiki/837716 "веполи").

### Запуск
**java – jar knitter_demo.jar**

После работы программы получаем схему в формате [Dot](https://graphviz.org/download/ "graphviz.org"), которая преобразуется в картинку в формате JPG. Если не сработало (jar сделан для Windows), то запустите следующую команду: 

**dot schem.dot -Tjpg -o schem.jpg**

### Пример
![](schem.jpg)
