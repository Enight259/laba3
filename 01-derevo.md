1. фрагмент вывода (pstree -p)
<img width="1917" height="1001" alt="image" src="https://github.com/user-attachments/assets/342d7a9a-e8f6-45b3-9a1a-e7d38298fe67" />
2. Цепочка от моей оболочки до PID1
<img width="1561" height="414" alt="image" src="https://github.com/user-attachments/assets/9c07b1fd-08c0-4fa4-bb2d-235011b006aa" />
3. Процесс который стоит в корне дерева это PID1, у него нет родителя потому что это первый процесс который запускает ядро при запуске системы, а PID1 запускает все следующие процессы.

4. <img width="1148" height="250" alt="image" src="https://github.com/user-attachments/assets/da0599b2-e154-40cb-bbca-2ba98a1fbcdd" />
Всего процессов у меня 287, а большинство из них находятся в состоянии S(slepping) для того что бы не нагружать система и выходят из него только тогда, когда с ними взаимодействуют.
