# Проект «Сшивка»

Данным интеллектуальным алгоритмом можно *автоматически* формировать схемы бизнес-процессов (BPMN), технологические карты, электрические схемы, UML диаграммы.

### Принцип действия

Генетический алгоритм согласно целевой функции формирует оптимальную схему процесса из функциональных блоков (базы данных), заданных в файле [in_schem.txt](in_schem.txt "in_schem.txt").  

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
![](schem.jpg)<br />

Было  &uarr;<br />
Стало &darr;<br />

------------
![](schem_new.jpg)<br />

В файле [synonyms.txt](synonyms.txt "synonyms.txt") добавляются синонимы для формирования функций-преобразователей. В каждой строчке по два через точку с запятой (;).
Результат: 
![](schem_synonyms.jpg)
**Решетка (#), поставленная в начале строки текстовых файлов, "выключает" строку.**

### Сшивка по диапазонам параметров 
При указании диапазов надо указывать латинские буквы, обозначающие физическую величину (t - температура, v - объем, m - масса итп).<br />
Пример: вода_t20, вода_t20-30, вода_t>=100, вода_v<1.5
![](schem_with_range.jpg)

### 'Заморозка' схемы
Из файла "schem.lst" (или из того, что задается в командной строке) загружается список соединений.<br />
Список состоит из строк вида [ИзФункции][Парам2][ВФункцию][Парам2].<br />
Сама программа генерирует строки [ИзФункции].[Парам2] - [ВФункцию].[Парам2]. Для наглядности.<br />
Если какие-то функции можно/нужно оптимизировать, то их соединения надо удалить из списка.<br />
[Подробнее тут](https://dzen.ru/media/maxzawalo/sshivka-zamorojennyi-genom-65829cfc910b21212106979a)

### [Поддержать проект](https://yoomoney.ru/to/410011136228964)