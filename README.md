# Домашнее задание к занятию 12 «GitLab»

## Основная часть

### DevOps

В репозитории содержится код проекта на Python. Проект — RESTful API сервис. Ваша задача — автоматизировать сборку образа с выполнением python-скрипта:

1. Образ собирается на основе [centos:7](https://hub.docker.com/_/centos?tab=tags&page=1&ordering=last_updated).
2. Python версии не ниже 3.7.
3. Установлены зависимости: `flask` `flask-jsonpify` `flask-restful`.
4. Создана директория `/python_api`.
5. Скрипт из репозитория размещён в /python_api.
6. Точка вызова: запуск скрипта.
7. При комите в любую ветку должен собираться docker image с форматом имени hello:gitlab-$CI_COMMIT_SHORT_SHA . Образ должен быть выложен в Gitlab registry или yandex registry.

   ![img](https://github.com/SeNike/Study_24/blob/main/GitLab/1.png)

### Product Owner

Вашему проекту нужна бизнесовая доработка: нужно поменять JSON ответа на вызов метода GET `/rest/api/get_info`, необходимо создать Issue в котором указать:

1. Какой метод необходимо исправить.
2. Текст с `{ "message": "Already started" }` на `{ "message": "Running"}`.
3. Issue поставить label: feature.

   ![img](https://github.com/SeNike/Study_24/blob/main/GitLab/2.png)

### Developer

Пришёл новый Issue на доработку, вам нужно:

1. Создать отдельную ветку, связанную с этим Issue.
2. Внести изменения по тексту из задания.
3. Подготовить Merge Request, влить необходимые изменения в `master`, проверить, что сборка прошла успешно.

  ![img](https://github.com/SeNike/Study_24/blob/main/GitLab/3.png)
  ![img](https://github.com/SeNike/Study_24/blob/main/GitLab/4.png)
  ![img](https://github.com/SeNike/Study_24/blob/main/GitLab/5.png)
  ![img](https://github.com/SeNike/Study_24/blob/main/GitLab/6.png)

### Tester

Разработчики выполнили новый Issue, необходимо проверить валидность изменений:

1. Поднять докер-контейнер с образом `python-api:latest` и проверить возврат метода на корректность.
2. Закрыть Issue с комментарием об успешности прохождения, указав желаемый результат и фактически достигнутый.

![img](https://github.com/SeNike/Study_24/blob/main/GitLab/2.png)

## Итог

В качестве ответа пришлите подробные скриншоты по каждому пункту задания:

- файл [gitlab-ci.yml](https://github.com/SeNike/09-ci-06-gitlab/blob/main/.gitlab-ci.yml);
- [Dockerfile](https://github.com/SeNike/09-ci-06-gitlab/blob/main/Dockerfile); 
- [лог успешного выполнения пайплайна](https://github.com/SeNike/09-ci-06-gitlab/blob/main/pipeline.log);
- решённый Issue.

