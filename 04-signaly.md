<img width="1904" height="1002" alt="image" src="https://github.com/user-attachments/assets/b07a9c99-d7c1-48c5-9f62-936dff7e117e" />
<img width="1155" height="309" alt="image" src="https://github.com/user-attachments/assets/26ae6396-a446-4f5b-aa43-d110ea3fd27e" />
<img width="1197" height="311" alt="image" src="https://github.com/user-attachments/assets/c2fcdb49-2762-4cee-b6eb-acf557d4f5f3" />
<img width="1170" height="422" alt="image" src="https://github.com/user-attachments/assets/669f53ec-6416-480c-b6ca-04d187219b40" />
<img width="1163" height="480" alt="image" src="https://github.com/user-attachments/assets/e02c0ab2-27f6-47f7-8938-bc2b0ff301b5" />
<img width="1158" height="296" alt="image" src="https://github.com/user-attachments/assets/f9270715-23ac-416a-bb70-1094f39edb74" />
<img width="1165" height="318" alt="image" src="https://github.com/user-attachments/assets/a96959e4-feaf-4814-b05f-a5c9fc8cb754" />
<img width="1162" height="272" alt="image" src="https://github.com/user-attachments/assets/925dd982-ef5d-4f6b-9c23-ed1f10129522" />
<img width="1160" height="297" alt="image" src="https://github.com/user-attachments/assets/f5516933-da38-43e7-b381-8e0ea06d7893" />
<img width="1115" height="300" alt="image" src="https://github.com/user-attachments/assets/134fb424-852b-4892-8db5-8697a2890acf" />
<img width="1131" height="361" alt="image" src="https://github.com/user-attachments/assets/b91dbb85-90b3-4802-888d-3e7049a029c5" />
1. SIGTERM можно и проигнорировать - программа сама решает, что делать. SIGKILL проигнорировать нельзя - ядро убивает процесс насильно, минуя саму программу.
2. Потому что SIGTERM даёт программе время корректно завершиться, а SIGKILL это крайняя мера, которая убивает процесс мгновенно и без предупреждения. При немедленном использовании kill -9 для процесса базы данных могут пострадать целостность данных, состояние ресурсов и стабильность системы.
3. После нажатия Ctrl+Z процесс sleep получает состояние T или остановлен.
4. CTRL +C это процесс завершается, а CTRL+Z это процесс приостанавливается, но остается в памяти.
