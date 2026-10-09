<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/2a0a6ee7-f546-46ca-911e-8fe9507f44e2" />
<img width="1193" height="256" alt="image" src="https://github.com/user-attachments/assets/668d9fd8-f2d1-4372-994b-2a49d8ce4dd7" />
<img width="1168" height="337" alt="image" src="https://github.com/user-attachments/assets/27968d64-fb57-42c9-b8f5-f1c473acdada" />
<img width="1166" height="376" alt="image" src="https://github.com/user-attachments/assets/4a9f3862-91f9-4188-a98f-94c64581e211" />
<img width="1171" height="311" alt="image" src="https://github.com/user-attachments/assets/a7817fce-9823-4c11-a53e-9c6ef79cb7a5" />
Процесс	PID	Владелец (USER)	Родитель (PPID)


Самозванец kworker	3400	user	3062 (bash)


Веб-сервер python3	3402	user	3062 (bash)


Первый признак это подозрительное имя пользователя. Команда: ps -eo pid,user,cmd | grep kworker. Найдено /tmp/kworker 3000 который показывается без скобочек. Подозрительно потому что так обычно пытаются маскироваться вредоносные программы, выдавая себя за поток ядра.


Признаки 2 и 3 это запуск временных каталогов. Команда: ls -l /proc/*/exe 2>/dev/null | grep -E '/tmp|/dev/shm|deleted'.Найдено: 3400 указывающее на /tmp/kworker и была помечена как удаленный, что означает файл был удалён с диска, но процесс продолжает работать в памяти. Подозрительно потому что /tmp - это место, куда может писать любой пользователь, поэтому вредоносное ПО часто запускается оттуда.


Признак 4 открытый сетевой порт. ps -eo pid,user,cmd | grep python. Найден процесс PID 3402, который слушает сетевой порт 8080. Подозрительно потому что Открытый наружу сетевой порт, обычные системные процессы не запускают веб-серверы на произвольных портах без ведома администратора.

Устранено было командой kill 3400 kill 3402. Вредоносные процессы были убиты.


/proc/PID/exe можно доверять, потому что это ссылка на реальный исполняемый файл, который ядро связывает с процессом.
