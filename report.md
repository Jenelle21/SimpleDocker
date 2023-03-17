## Part 1. Готовый докер

* Взять официальный докер образ с **nginx** и выкачать его при помощи `docker pull`
* Проверить наличие докер образа через `docker images`\
![dock1](Screenshots/dock1.png)
* Запустить докер образ через `docker run -d [image_id|repository]`
* Проверить, что образ запустился через `docker ps`\
![dock2](Screenshots/dock2.png)
* Посмотреть информацию о контейнере через `docker inspect [container_id|container_name]`
* По выводу команды определить и поместить в отчёт размер контейнера, список замапленных портов и ip контейнера\
![dock3](Screenshots/dock3.png)\
![dock4](Screenshots/dock4.png)
* Остановить докер образ через `docker stop [container_id|container_name]`
* Проверить, что образ остановился через `docker ps`\
![dock5](Screenshots/dock5.png)
* Запустить докер с замапленными портами 80 и 443 на локальную машину через команду `run`
* Проверить, что в браузере по адресу localhost:80 доступна стартовая страница **nginx**\
![dock6](Screenshots/dock6.png)\
![dock7](Screenshots/dock7.png)
* Перезапустить докер контейнер через `docker restart [container_id|container_name]`
* Проверить любым способом, что контейнер запустился
![dock8](Screenshots/dock8.png)

## Part 2. Операции с контейнером

* Прочитать конфигурационный файл *nginx.conf* внутри докер контейнера через команду `exec`\
![dock9](Screenshots/dock9.png)
* Создать на локальной машине файл *nginx.conf*
* Настроить в нем по пути */status* отдачу страницы статуса сервера **nginx**\
![dock10](Screenshots/dock10.png)
* Скопировать созданный файл *nginx.conf* внутрь докер образа через команду `docker cp`
* Перезапустить nginx внутри докер образа через команду `exec`
* Проверить, что по адресу *localhost:80/status* отдается страничка со статусом сервера **nginx**\
![dock11](Screenshots/dock11.png)
* Экспортировать контейнер в файл container.tar через команду export
* Остановить контейнер
![dock12](Screenshots/dock12.png)
* Удалить образ через docker rmi [image_id|repository], не удаляя перед этим контейнеры
![dock13](Screenshots/dock13.png)
* Удалить остановленный контейнер
![dock14](Screenshots/dock14.png)
* Импортировать контейнер обратно через команду import
* Запустить импортированный контейнер\
![dock15](Screenshots/dock15.png)
* Проверить, что по адресу localhost:80/status отдается страничка со статусом сервера nginx\
![dock16](Screenshots/dock16.png)