University: [ITMO University](https://itmo.ru/ru/)\
Faculty: [FICT](https://fict.itmo.ru)\
Course: [Введение в веб технологии](https://itmo-ict-faculty.github.io/introduction-in-web-tech/)\
Year: 2025/2026\
Group: U4125\
Author: Eliseeva Polina Fedorovna\
Lab: Lab1\
Date of create: 11.03.2026 \
Date of finished: 12.03.2026

# Лабораторная работа №1
## Основы работы с Docker

## Цель работы

Изучить основы контейнеризации с использованием Docker: установку Docker, работу с готовыми образами, запуск и управление контейнерами, а также использование томов для сохранения данных.

## Используемое окружение

Работа выполнялась на операционной системе Windows с использованием Docker Desktop, WSL и Git Bash.

## Ход работы

1. Установка Docker, команда hello-world подтвердила, что Docker установлен корректно и способен скачивать образы и запускать контейнеры.
После этого были изучены базовые команды Docker.
<img width="952" height="871" alt="image" src="https://github.com/user-attachments/assets/ddece809-25e2-40b0-b7bc-6b0aebb80cdf" />

2. Скачала образ Ubuntu
<img width="864" height="150" alt="image" src="https://github.com/user-attachments/assets/0a911520-4d96-49b7-9843-c5e3a50d6f0b" />

После этого был запущен интерактивный контейнер, Внутри контейнера были выполнены команды. Таким образом была проверена возможность установки пакетов внутри контейнера и работа с Linux-средой в Docker. 
<img width="1027" height="867" alt="image" src="https://github.com/user-attachments/assets/00006fd9-9ed5-4173-960f-71bc9a9e8e7d" />
<img width="952" height="225" alt="image" src="https://github.com/user-attachments/assets/3a729100-fd5f-46eb-a43b-6a4138c87b8c" />

3. Запустила контейнер
<img width="932" height="414" alt="image" src="https://github.com/user-attachments/assets/fde3e6b4-c027-435f-ab4f-8f001d06a3b9" />

Проверила работу в браузере и посмотрела логи
<img width="945" height="594" alt="image" src="https://github.com/user-attachments/assets/4eb9b75d-3ebd-4547-bd0d-8deb9e3b8334" />

4. Для изучения управления контейнерами были использованы команды:

docker ps
docker ps -a
docker stop web-server
docker start web-server
docker rm web-server
docker rmi nginx:alpine

С помощью этих команд был просмотрен список контейнеров, выполнена остановка контейнера, его повторный запуск, удаление контейнера и затем удаление образа nginx:alpine.

<img width="945" height="391" alt="image" src="https://github.com/user-attachments/assets/11527cb4-bb2c-48c7-b29c-eadd3c4006e2" />

Управление контейнерами:остановка, запуск, удаление
<img width="944" height="985" alt="image" src="https://github.com/user-attachments/assets/f38cad98-7039-4fc8-b899-d1800fe9031c" />

5. Работа с томами.Для изучения механизма постоянного хранения данных был создан том:

docker volume create my-volume

После этого был запущен контейнер с подключённым томом:
docker run -it --name volume-test -d -v my-volume:/data ubuntu bash

Внутри контейнера был создан файл.
После этого была выполнена попытка удалить контейнер, однако Docker сообщил, что контейнер нельзя удалить, пока он находится в запущенном состоянии.
Поэтому контейнер был сначала остановлен, а затем удален.

После этого был создан новый контейнер с тем же томом:
docker run -it --name volume-test2 -v my-volume:/data ubuntu bash

Внутри нового контейнера была выполнена проверка:
cat /data/test.txt
Файл сохранился, а содержимое Hello from volume осталось доступным. Это подтвердило, что Docker volume хранит данные независимо от жизненного цикла контейнера.
<img width="947" height="605" alt="image" src="https://github.com/user-attachments/assets/a1bab993-c991-4e8d-b5b8-605fea2186e3" />

В результате выполнения лабораторной работы:

установлен и настроен Docker
изучены базовые команды Docker
получен опыт работы с готовыми образами
выполнен запуск и управление контейнерами
изучен механизм работы томов Docker
подтверждено сохранение данных при использовании volumes

В ходе выполнения лабораторной работы были изучены основные принципы контейнеризации и базовые сценарии работы с Docker.

