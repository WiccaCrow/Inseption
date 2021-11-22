# Inseption
Docker/Docker Compose.

Проект по системному администрированию.

В проекте настроена инфраструктура из служб:
  - adminer
  - mariadb
  - mysite
  - nginx
  - redis
  - vsftpd
  - wordpress
 
 А также создан статический сайт.
 
 Чтобы ознакомиться с сайтом, необходимо запустить проект.
 Статический сайт написан на HTML/CSS.
 Когда проект будет запущен (см.п.4), используя 443 порт (или https) в адресную строку в браузере введите (см.п.4):
  https://localhost:443/resume/
                              либо
  https://mdulcie.42.fr:443/resume/
  
!!! Важно /resume/ именно так ввести (т.е. с косой чертой в конце - это жестко прописано в конфигурации службы nginx).

Или просто открыть используя браузер Inception/Project_for_VirtBox/srcs/requirements/mysite/resume.html для ознакомления со статическим сайтом.

Для каждой службы написан собственный Dockerfile, с помощью которого я создаю образ (без использования чужих готовых образов, в том числе без использования сервиса DockerHub (Alpine / Debian исключены из этого правила).).

____________________________________________
Запустить проект можно следующими способами:
1. Используя файлы из папки Project_for_VirtBox (по  subject).
    Эта папка используется для запуска проекта на виртуальной машине.
    
    Можно также использовать и без виртуальной машины на Ubuntu см.п.3.1.
    
    При запуске Makefile использует команду с sudo, необходимо будет ввести пароль.
    
2. Используя файлы из Project_for_ubuntu_mac.

____________________________________________
Подготовка к старту проекта.

1. Скачать репозиторий Inception.

2. Зайти в папку, из которой выбран запуск проекта.

3.1. Project_for_VirtBox. В папке есть инструкция readme.
        Project for Ubuntu_20.04 (on VM).
        You need to edit the file /etc/hosts, replace localhost to mdulcie.42.fr
    
    Исполнение данной инструкции необходимо для того, чтобы в браузере можно было ввести в адресную строку mdulcie.42.fr.
    Также можно все это проделать и без установки виртуальной машины, просто не забудьте поменять в файле /etc/hosts, обратно на localhost текст mdulcie.42.fr
    
3.2. Project_for_ubuntu_mac.В папке есть инструкция readme.

        Для запуска проекта, необходимо:
        
        1) зайти в папку srcs 
        
        2) в этой папке открыть файл docker-compose-mac.yml (для MacOS) или docker-compose-ubuntu.yml  (для Ubuntu).
        
        3) и внизу в файле в строках (99, 106, 113) "device:    
            /home/user/Desktop/github/(продолжение пути до подключаемых volumes)" заменить часть "/home/user/Desktop/github/" на путь на Вашей машине до проекта Inception если был скачан весь репозиторий Inception, 
              либо
            если была скачана только папка Project_for_ubuntu_mac заменить часть пути "/home/user/Desktop/github/Inception/" на путь на Вашей машине до папки  Project_for_ubuntu_mac.
____________________________________________
Старт.

перейти в папку Project_for_VirtBox, запустить Makefile.
    либо
перейти в папку Project_for_ubuntu_mac, запустить Makefile -f (файл для выбранной системы Makefile-mac либо Makefile-ubuntu). 

4. Когда проект запущен, все службы заработали, в браузере в адресной строке необходимо ввести:
            https://localhost:443     при использовании Project_for_ubuntu_mac
            https://mdulcie.42.fr:443     при использовании Project_for_VirtBox
            
            Соответственно для просмотра статического сайта:
              https://localhost:443/resume/
                              либо
              https://mdulcie.42.fr:443/resume/
              
  Приятного просмотра и хорошего дня!!!
