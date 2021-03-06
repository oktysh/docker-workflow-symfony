Процесс разработки
==================

## Разработка

В репозитории разработчика присутствует protected-ветка `stable` и свою работу над
задачей он должен начинать с создания новой ветки, указывающую в тоже место, что и `stable`

```bash
git fetch --all --prune
git checkout origin/stable
git checkout -b feature-qwerty
git push origin feature-qwerty
```

На каком-то этапе, когда нужно выложить свои изменения в на тестовый сайт,
нужно залить изменения в ветку `master`

```bash
git fetch --all --prune
git branch -d master
git checkout master
git merge feature-qwerty
git push origin master
```

Все изменения будут выложены на тестовый сайт разработчика и
должны быть приняты менеджером проекта.

## Staging

Слияние изменений из репозитория разработчика в основной должно
происходить из ветки задачи, в примере - это `feature-qwerty`, в ветку
`master` основного репозитория.

После проверки выполнения задачи менеджером, разработчик должен создать
соответствущий Merge Request в Web-интерфейсе GitLab.
 
Перед принятием Merge Request администратор должен убедиться, что коммиты
в ветке разработчика идут строго после текущего положения ветки `stable`.

## Production

Для выкатки изменений на рабочий сайт, нужно создать в Web-интерфейсе
тэг `release-*`
