## Итак стоит задача развернуть локально Jenkins на Ubuntu Server 20.04 в VMWare WorkStation.
1. Установим Java<br>
catware@jenkins-vp:~$ sudo apt-get install openjdk-8-jre<br>
2. Добавим ключ репозитория и выполним apt-get update<br>
catware@jenkins-vp:\~$ curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \<br>
\>   /usr/share/keyrings/jenkins-keyring.asc > /dev/null<br>
catware@jenkins-vp:\~$ echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \<br>
\>   https://pkg.jenkins.io/debian-stable binary/ | sudo tee \\<br>
\>   /etc/apt/sources.list.d/jenkins.list \> /dev/null<br>
3. Установим Jenkins<br>
catware@jenkins-vp:~$ sudo apt-get install jenkins<br>
4. Jenkins сразу устанавливается как service, соответственно можно посмотреть его статус:<br>
catware@jenkins-vp:~$ sudo service jenkins status<br>
5. Jenkins установлен и запущен по умолчанию на порту 8080. Зайти на него можно через браузер *статический ip машины*:8080<br>
https://prnt.sc/mAVFX9PoQlz7<br>
6. Для того чтобы "разблокировать" Jenkins необходимо посмотреть пароль администратора по пути /var/lib/jenkins/secrets/initialAdminPassword:<br>
catware@jenkins-vp:~$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword<br>
7. Финальный этап это кастомизация. Можно установить рекомендуемые плагины, а можно выбрать что устанавливать.<br>
https://prnt.sc/Djc3D1NbzLrI<br>
## Установка Jenkins выполнена
