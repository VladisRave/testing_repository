# Описание курса

Данный практикум предназначен для студентов первого курса, которые впервые знакомятся с системой контроля версий Git и платформой GitHub.

В ходе двух занятий студенты:

- Установят Git
- Настроят Git
- Создадут аккаунт GitHub
- Создадут репозиторий
- Клонируют репозиторий
- Создадут файл резюме
- Научатся добавлять файлы в Git
- Сделают commit
- Отправят изменения в GitHub
- Научатся работать с ветками
- Освоят базовый workflow разработки

---

# Занятие 1. Основы Git и создание резюме

# Цель занятия

Познакомиться с Git, GitHub и создать первый репозиторий с резюме.

---

# Шаг 1. Установка Git

Перейдите на официальный сайт Git:

[https://git-scm.com/downloads](https://git-scm.com/downloads)

Скачайте версию для Windows.

Запустите установщик.

Во время установки можно оставить параметры по умолчанию.

Нажимайте:

Next → Next → Next → Install

После установки откройте программу Git Bash.

Git Bash можно найти через поиск Windows:

Пуск → Git Bash

---

# Шаг 2. Проверка установки Git

Откройте Git Bash и выполните команду:

```bash
git --version
```

Если Git установлен правильно, появится версия Git.

Например:

```
git version 2.44.0
```

---

# Шаг 3. Настройка Git

Перед началом работы необходимо указать имя пользователя и email.

Введите команды:

```bash
git config --global user.name "Ваше Имя"
git config --global user.email "your@email.com"
```

Пример:

```bash
git config --global user.name "Ivan Ivanov"
git config --global user.email "ivan@mail.com"
```

Проверка настроек:

```bash
git config --list
```

---

# Шаг 4. Создание аккаунта GitHub

Перейдите на сайт:

[https://github.com](https://github.com/)

Создайте аккаунт.

После регистрации выполните вход.

---

# Шаг 5. Создание репозитория

После входа в GitHub:

1. Нажмите кнопку New repository
2. Введите название репозитория

Название:

```
my-first-repo
```

Параметры:
- Public
- Add README file

Нажмите кнопку Create repository.

---

# Шаг 6. Клонирование репозитория

После создания репозитория:
1. Нажмите кнопку Code
2. Выберите HTTPS
3. Скопируйте ссылку    

Пример ссылки:

```
https://github.com/username/my-first-repo.git
```

Откройте Git Bash

Перейдите на рабочий стол:

```bash
cd Desktop
```

Выполните команду клонирования:

```bash
git clone https://github.com/username/my-first-repo.git
```

Перейдите в папку проекта:

```bash
cd my-first-repo
```

---

# Шаг 7. Создание файла резюме

Создайте файл resume.txt

```bash
touch resume.txt
```

Откройте файл:

```bash
notepad resume.txt
```

---

# Как составить резюме первокурснику

Рекомендуемая структура резюме:

```
Имя Фамилия

Контактная информация
Email
Телефон

Цель

Образование

Навыки

Проекты

Дополнительная информация
```

Пример резюме:

```
Иван Иванов

Email: ivan@mail.com
Телефон: 000000000

Цель
Получение первой позиции Junior Developer

Образование
ИТ колледж
Специальность: Программирование

Навыки
HTML
CSS
Git

Проекты
Резюме проект

Дополнительная информация
Ответственный
Быстро обучаюсь
```

Сохраните файл.

---

# Шаг 8. Добавление файла в Git

Проверьте статус:

```bash
git status
```

Добавьте файл:

```bash
git add resume.txt
```

Добавить все файлы:

```bash
git add .
```

---

# Шаг 9. Создание commit

```bash
git commit -m "Добавлено резюме"
```

---

# Шаг 10. Отправка изменений на GitHub

```bash
git push
```

Если push выполняется впервые:

```bash
git push origin main
```

---

# Проверка результата

Перейдите на GitHub

Обновите страницу

Вы увидите файл resume.txt

---

# Полный цикл работы

```bash
git add .
git commit -m "message"
git push
```

---

# Практическое задание (Занятие 1)

Студенты должны:
1. Установить Git
2. Создать GitHub аккаунт
3. Создать репозиторий my-first-repo
4. Клонировать репозиторий
5. Создать файл resume.txt
6. Заполнить резюме
7. Добавить файл в Git
8. Сделать commit    
9. Сделать push

---

# Занятие 2. Работа с ветками

# Цель занятия

Научиться работать с ветками и организовывать процесс разработки.

---
# Что такое ветки

Ветки позволяют разрабатывать новые функции независимо от основной версии проекта.

Основные ветки проекта:
- main
- development
- testing
- production    

---

# Создание ветки development

```bash
git checkout -b development
```

Отправка ветки:

```bash
git push -u origin development
```

---

# Создание ветки testing

```bash
git checkout -b testing
```

```bash
git push -u origin testing
```

---

# Создание ветки production

```bash
git checkout -b production
```

```bash
git push -u origin production
```

---

# Просмотр веток

```bash
git branch
```

---

# Переключение между ветками

```bash
git checkout main
```

```bash
git checkout development
```

---

# Работа в ветке

Создайте файл:

```bash
touch about.txt
```

Добавьте файл:

```bash
git add .
```

Commit:

```bash
git commit -m "Добавлен файл about"
```

Push:

```bash
git push
```

---

# Слияние веток

Перейти в main:

```bash
git checkout main
```

Слить ветку development:

```bash
git merge development
```

Отправить изменения:

```bash
git push
```

---

# Рекомендуемый workflow

```bash
git checkout development
работа
git add .
git commit -m "feature"
git push

git checkout testing
git merge development

git checkout main
git merge testing
```

---

# Практическое задание (Занятие 2)

Студенты должны:
1. Создать ветку development
2. Создать ветку testing
3. Создать ветку production
4. Сделать изменения
5. Сделать commit
6. Сделать push
7. Сделать merge    

---

# Полезные команды

```bash
git status
git add .
git commit -m "message"
git push
git pull
git branch
git checkout
git merge
```

---

# Результат курса

После прохождения курса студент должен уметь:
- Работать с Git
- Работать с GitHub
- Создавать репозитории
- Работать с ветками
- Выполнять merge
- Работать с командной строкой 