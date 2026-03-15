University: [ITMO University](https://itmo.ru/ru/)\
Faculty: [FICT](https://fict.itmo.ru)\
Course: [Введение в веб технологии](https://itmo-ict-faculty.github.io/introduction-in-web-tech/)\
Year: 2025/2026\
Group: U4125\
Author: Eliseeva Polina Fedorovna\
Lab: Lab0\
Date of create: 15.03.2026 \
Date of finished: 15.03.2026

Настройка CI/CD пайплайна с GitHub Actions:

Подготовка проекта:
1. Создала новый репозиторий и файлы app.py, requirements.txt, Dockerfile

Создать аккаунт на Docker Hub (если нет)
Создать новый репозиторий на Docker Hub для вашего образа
Настройка GitHub Actions:

Создать папку .github/workflows/ в корне проекта
Создать файл docker-build.yml с пайплайном, который должен:
Запускаться при пуше в main ветку
Использовать Ubuntu как runner
Выполнять checkout кода
Настраивать Docker Buildx
Логиниться в Docker Hub используя секреты
Собирать и пушить образ с тегом username/my-flask-app:latest
Добавлять шаг деплоя (можно просто echo сообщение)
Настройка секретов:

В настройках GitHub репозитория добавить секреты:
DOCKER_USERNAME - ваш логин на Docker Hub
DOCKER_PASSWORD - ваш пароль или токен доступа Docker Hub
Тестирование пайплайна:

Сделать коммит и пуш в main ветку
Проверить выполнение пайплайна в разделе Actions
Убедиться, что образ появился в Docker Hub
Проверить логи выполнения каждого шага
