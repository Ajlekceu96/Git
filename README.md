# Инструкция для работы с Git и удалёнными репозиториями GitHub

---

## Что такое Git?

<img src="GitLogo.png" alt="Git logo" width="500"/>

**Git** - это одна из реализаций распределённых систем контроля версий, имеющая как и локальные, так и удалённые репозитории. Является самой популярной реализацией систем контроля версий в мире.

[https://git-scm.com/downloads](https://git-scm.com/downloads) - официальный сайт GitHub

## Что такое GitHub

<img src="Octocat.png" alt="GitHub octocat" width="500"/>

**GitHub** — это крупнейший веб-сервис для хостинга IT-проектов и их совместной разработки.
Веб-сервис основан на системе контроля версий Git и разработан на Ruby on Rails и Erlang компанией GitHub, Inc.

C помощью GitHub над кодом проекта может работать неограниченное количество программистов из любых точек мира. В GitHub есть система контроля (управления) версий **Git**: сервис позволяет просматривать и контролировать любые изменения кода любым разработчиком и возвращаться к состоянию до изменений.

В целом GitHub — это **социальная сеть** для разработчиков, в которой можно найти проекты с открытым кодом от других разработчиков, практиковаться в написании кода и хранить свое **портфолио**.

[https://github.com/](https://github.com/) - официальный сайт GitHub

---

## Начальная настройка и работа с удаленными репозиториями

### 1. Установка и настройка Git

#### Установка Git

Для того, чтобы **скачать Git**, нужно перейти по ссылке: [https://git-scm.com/downloads](https://git-scm.com/downloads)
Выбрать свою **операционную систему** и разрядость, начнётся загрузка установочного файла.
После чего **установить Git**, согласно **иструкции**.

#### Настройка Git

Теперь, когда Git установлен в вашей системе, самое время настроить среду для работы с Git под себя. Это нужно сделать только один раз — при обновлении версии Git настройки сохранятся. Но, при необходимости, вы можете поменять их в любой момент, выполнив те же команды снова.

**Первое**, что вам следует сделать после установки Git — указать **ваше имя** и **адрес электронной почты**.
Это важно, потому что каждый коммит в Git содержит эту информацию, и она включена в коммиты, передаваемые вами

> Все команды для работы Git, вводятся в **терминал**
Вы можете использовать приложение(командной строки Git) **Git Bash**, предоставляемое
компанией Git.
Git Bash устанавливается вместе с остальными компонентами GIt

> Также вы можете использовать **терминал** встроенный в **IDE**, которую вы будите использовать

Запустите **териминал** и введите в консоль команды:

```Git
git config --global user.name "Ваш_имя_или_никнейм"
git config --global user.email Ваш_эмэйл
```

**Далее**, настроим **ветку по умолчанию**
Когда вы инициализируете репозиторий командой **git init**, Git создаёт ветку с именем **master** по умолчанию.
Начиная с версии 2.28, вы можете задать другое имя для создания **ветки по умолчанию**.

> Главную ветку принято называть **main**
> Также встречаются случаи, когда главная ветка называется **master**

Чтобы установить имя **main** для вашей **ветки по умолчанию**, выполните следующую команду:

`git config --global init.defaultBranch main`

>Чтобы посмотреть все установленные настройки, используйте команду:

`git config --list`

### 2. Создание аккаунта в Github

Первый шаг к использованию сервиса GitHub заключается в регистрации нового пользователя. В процедуре нет ничего сложного – достаточно зайти на [официальный сайт](https://github.com/) и создать новую **учетную запись**.

**Имя пользователя**, как и **email**, проверяется на занятость, и придется выбирать тот, с которым платформа позволит продолжать регистрацию.

**Пароль** вводится на выбор пользователя, но с учетом правил. Так, рекомендуется комбинация размером в 15 символов или 8, но с использованием хотя бы одной цифры и строчной буквы.

Далее нужно указать, хочется ли получать новости об обновлениях продуктов и самой системы. Последним шагом становится подтверждение – пользователю предлагается собрать паззл, после чего станет активной кнопка **[Зарегистрироваться]**.

Вход на платформу будет открыт только после подтверждения электронной почты, поэтому зайти анонимно не получится. Это своеобразная защита сервера от многочисленных ботов и гарантия для пользователей, что они будут общаться с реальными людьми. Теперь можно приступать к управлению настройками внутри личного кабинета.

### 3. Создание репозитория

* Нажать на кнопку [[Create a new repository]](https://github.com/new).
* Ввести название и описание репозитория.
* Выбрать видимость репозитория **[Public]** или **[Private]**.
* Нажать на кнопку **[Create repository]**.
* Открываем в **терминале** папку с вашим **проект**
Для того, чтобы перейти в папку с вашем проектом, используйте команду:
`cd Путь_до_каталога_с_вашим_проектом`
например:
`cd C:\MyProjects\Project1`

* После чего в **терминале** вашего **нового** проекта по очередно вводите команды:

```Git
echo "# Git" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Ваш_никнейм/Название_репозитория.git
git push -u origin main
```

* Если проект у вас **уже был** и был подключен **контроль версий**, то используйте следующие команды:

```Git
git remote add origin https://github.com/Ваш_никнейм/Название_репозитория.git
git branch -M main
git push -u origin main
```

### 4. Создание коммитов

#### Добавление изменений

Для добавления измений в используется команда:

`git add`

Чтобы добавить **все** изменения, используйте команду:

`git add *`

#### Просмотр состояния репозитория

Для того, чтобы посмотреть состояние репозитория используется команда:

`git status`

Вы увидите были ли измения в файлах, или их не было.

#### Создание коммитов

Для того, чтобы создать коммит(сохранение) необходимо выполнить команду:

`git commit -m "Ваш_комментарий_к_коммиту"`

Все файлы для коммита должны обязательно быть **добавлены** командой **add**, а также должен быть прописан **комментарий** к коммиту.

### 5. Журнал изменений и перемещение между сохранениями

#### Журнал коммитов

Для того, чтобы посмтреть все сделанные **изменения** в репозитории, используется команда:

`git log`

После будут выведены все ваши коммиты, где можно посмотреть **Номер_коммита**

Команда **log** может принимать различные параметры:

* Параметр **--oneline** выводит каждый коммит в одну строку, что удобно если вы просматриваете большое количество коммитов, используется команда:

`git log --oneline`

* Параметр **--format**, позволяет вам полностью создать собственный формат вывода лога. Это особенно полезно, когда вы создаёте отчёты для автоматического разбора (парсинга) — поскольку вы явно задаёте формат и уверены в том, что он не будет изменяться при обновлениях Git'а:

```Git
git log --format:"%h - %an, %ar : %s"

Пример работы, данной команды:
номер_коммита - автор, дата : комментарий
номер_коммита - автор, дата : комментарий
номер_коммита - автор, дата : комментарий
```

Полезные опции для команды **git log --format** отображают наиболее полезные опции для изменения формата
*Таблица 1. Полезные опции для git log --format*

Параметр  | Описание выводимых данных
--------- | -------------
%H        | Хеш коммита
%h        | Сокращённый хеш коммита
%T        | Хеш дерева
%t        | Сокращённый хеш дерева
%P        | Хеши родительских коммитов
%p        | Сокращённые хеши родительских коммитов
%an       | Имя автора
%ae       | Электронная почта автора
%ad       | Дата автора (формат соответствует параметру `--date=`)
%ar       | Дата автора, относительная (пр. "2 мес. назад")
%cn       | Имя коммитера
%ce       | Электронная почта коммитера
%cd       | Дата коммитера
%cr       | Дата коммитера, относительная
%s        | Комментарий

#### Перемещение между коммитами

Для того, чтобы **перемещаться** между коммитами, используется команда:

`git checkout Номер_коммита`

### 6. Ветки в Git

Чтобы узнать, какие ветки доступны и как называется текущая ветка, выполните команду:

`git branch`

#### Создание ветки

Для того, чтобы создать ветку, используется команда:

`git branch Название_новой_ветки`

#### Переключение веток

Для переключения на существующую ветку, используется команда:

`git checkout Название_ветки`

Команда **git checkout** также принимает аргумент **-b**, который действует как вспомогательный метод, позволяя создать новую ветку и сразу переключиться на нее.

`git checkout -b Название_новой_ветки`

#### Слияние веток

Команда **git merge** объединяет несколько последовательностей коммитов в общую историю. Чаще всего команду **git merge** используют для объединения двух веток.

Для того чтобы добавить ветку в **текущую** используется команда:

`git merge Название_ветки`

Перед слиянием следует предпринять несколько подготовительных действий, чтобы операция прошла без проблем.
**Порядок слияния веток:**

* **Проверка выбора принимающей ветки**
Выполните команду **git status**. Это позволит убедиться, что **HEAD** указывает на ветку, **принимающую результаты** слияния. При необходимости выполните команду **git checkout Название_принимающей_ветки**, чтобы переключиться на принимающую ветку.
* **Получение последних коммитов из удаленного репозитория**
Убедитесь, что в принимающей ветке и ветке для слияния содержатся последние изменения из удаленного репозитория. Выполните команду **git fetch**, чтобы получить из него последние коммиты. Затем убедитесь, что в ветке **main** также содержатся последние изменения. Для этого выполните команду **git pull**.
* **Выполнение слияния**
После указанных выше действий по подготовке можете приступать к слиянию. Для этого выполните команду **git merge Название_ветки**, где **Название_ветки** — название ветки, которая будет объединена с принимающей (текущей).

#### Удаление веток

Для удаления ветки ввести команду:

`git branch -d Название_ветки`

### 7. Онлайн-репозиторий

#### Загрузка изменений

Чтобы загрузить изменения в онлайн-репозиторий введем команду:

`git push origin Название_ветки_в_удаленном_репозитории`

#### Получение изменений

Команда **git fetch** получает с сервера все изменения, **которых у вас ещё нет**, но **не будет изменять состояние** вашей рабочей копии.

`git fetch origin`

Эта команда просто получает данные и позволяет вам **самостоятельно** сделать слияние.

`git fetch origin Название_ветки_в_удаленном_репозитории`

То же, что и приведенная выше команда, но только получает изменения из **указанной ветки**.
Тем не менее, существует команда **git pull**, которая в большинстве случаев является командой **git fetch**, за которой непосредственно следует команда **git merge**.

### 8. Работа в команде

#### Клонирование существующего репозитория

Для получения копии существующего Git-репозитория, например, проекта, в который вы хотите внести свой вклад, необходимо использовать команду:

`git clone Ссылка_на_удаленный_репозиторий`

Для того, чтобы клонировать репозиторий в каталог с именем, отличающимся от того что в удаленном репозитории, необходимо указать желаемое имя, как параметр командной строки:

`git clone Ссылка_на_удаленный_репозиторий Имя_директории`

Эта команда делает всё то же самое, что и предыдущая, только результирующий каталог будет назван именем, что вы укажете.

#### Создание запросов слияния Pull Request в Github

При подключении к работе сторонних специалистов может понадобиться функция запроса слияния **Pull Request**. Инструмент для работы в таком формате называется **DIFF**. Он подчеркивает любые «**чужие**» изменения, чтобы владелец программы сразу видел, где код писал не он. Пометки будут доступны только после создания коммита.

Последовательность действий:

1. На сайте GitHub открыть репозиторий с которым вы хотите работать
2. Открыть вкладку **[Pull Request]**.
3. Нажать на кнопку **[Create Pull Request]**.
4. Выбрать ветку, которую следует слить с основной.
5. Просмотреть внесенные изменения.
6. После изучения информации созданный запрос на слияние подтверждается и новый код будет импортирован в основную ветку.

### 9. Отчеты об ошибках

Платформа **GitHub** используется не только для совместной разработки, а еще и для получения **обратной связи** с пользователями продуктов. Так, на вкладке **[Issue]**, например **тестировщик** может оставить сообщение о найденных им проблемах, с которыми ему пришлось столкнуться при использовании ПО. Чтобы сделать это, нужно нажать кнопку **[New issue]**.

После этого вносится **заголовок** и **текст сообщения**. **«Проблема»** отправляется нажатием на кнопку **[Create new issue]**.
**Владелец ветки** получает уведомления в личном кабинете или на электронную почту, указанную при регистрации.

### 10. Заключение

Финалом разработки обычно становится выпуск определенного **релиза** программного продукта. Это отражается на вкладке **[Releases]**. Здесь следует нажать на кнопку **[Create New Release]**, указать номер версии в поле **[Tag Version]**, внести ее **название** и небольшое **описание**. Здесь же прикрепляются архивы с **компилированными файлами**.

Если вы готовы опубликовать свой релиз, нажмите **[Publish Release]**.
Чтобы работать над релизом позже, нажмите **[Save Draft]**.

---

## Подборка полезных ресурсов

1. [https://git-scm.com/book/ru/v2](https://git-scm.com/book/ru/v2) - книга "Pro Git" официальном сайте Git.

2. [https://training.github.com/downloads/ru/github-git-cheat-sheet/](https://training.github.com/downloads/ru/github-git-cheat-sheet/) - шпаргалка по Git от GitHub.

3. [https://githowto.com/ru](https://githowto.com/ru) - онлайн-курс, который познакомит вас с основами Git.
