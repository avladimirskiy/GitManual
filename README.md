# GitManual
Проект-помощник по работе с git


Инициализация
```bash
git init
```

Статус репозитория
```bash
git status
```

Добавление файлов
```bash
git add . //если нужно добавить все изменения<br>
git add README.md //добавление конктреного файла<br>
```


Пример добавления коммита
```bash
git commit -m "Изменения в файле Readme" <br>
```

Отправяляем на сервер
```bash
git push https://github.com/avladimirskiy/GitManual.git<br>
```

Клонирование репозитория
```bash
git clone https://github.com/avladimirskiy/GitManual.git<br>
```

Лог
```bash
git log
```

Сокращенный лог
```bash
git log --oneline<br>
```

<p>
HEAD -- это голова.
Коммит -- это всему голова.
Статусы файлов:
</p>

<p>
В выводе команды git log --oneline умещается максимум 72 первых символа сообщения, поэтому многие правила включают пункт: «Сообщение не должно быть длиннее 72 символов»
</p>

```bash
git commit -m "Добавить урок про оформление сообщений коммитов"
```

<p>
Вот пример полезного сообщения в репозитории новостного сайта: Исправление опечатки в заголовке главной страницы на хорватском. Такое сообщение даёт много информации:
Исправление опечатки значит, что исправлена ошибка, которая была допущена при наборе. Такое исправление не меняет смысл. То есть, например, главному редактору не нужно перепроверять этот заголовок.
На хорватском говорит о том, что переводчикам на другие языки этот коммит можно смело пропускать.
В заголовке главной страницы указывает, где произошли изменения. Если, например, кто-то зайдёт на сайт и ему не понравится новый заголовок, он легко найдёт по истории (git log) автора этого коммита и спросит у него, почему заголовок теперь такой.
</p>

<p>Без единообразия коммитов нет и эффективной работы в Git. Это может показаться мелочью, но когда коммиты с сообщениями в разных стилях идут друг за другом, их может быть сложно читать.
Чтобы упростить работу, команды или даже целые компании часто договариваются об определённом стиле (то есть о правилах) оформления сообщений коммитов.
Например, правила могут быть такие:
длина сообщения от 30 до 72 символов;
первое слово — глагол в инфинитиве («исправить», «дополнить», «добавить» и другие);
и так далее.</p>


<h3>Корпоративный</h3>
<p>Во многих компаниях применяется Jira — система для организации проектов и задач. У каждой задачи в Jira есть идентификатор из нескольких заглавных латинских букв и номера. Например, LGS-239 значит, что это 239-я задача в проекте LGS (сокращение от англ. logistics — «логистика»).
В корпоративном стиле в начале сообщения обычно указывают Jira-ID, а после — текст сообщения.
</p>

``` bash
git commit -m "LGS-239: Дополнить список пасхалок новыми числами" </p>
```

<h3>Стандарт Conventional Commits </h3>
<p>(англ. «соглашение о коммитах») отличается качественной документацией и подробной проработкой. Он подходит для репозиториев с исходным кодом программ. Использовать его для других типов проектов (например, для перевода книги) было бы неудобно.
Conventional Commits предлагает такой формат коммита: <type>: <сообщение>. Первая часть type — это тип изменений. Таких типов достаточно много. Вот два примера:
feat (сокращение от англ. feature) — для новой функциональности;
fix (от англ. «исправить», «устранить») — для исправленных ошибок.
Более подробный список можно увидеть на сайте с описанием этого стиля <a src="https://www.conventionalcommits.org/ru/v1.0.0-beta.4/#%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F">Ссылка</a>.
Например, сообщение может быть таким.</p>

``` bash
git commit -m "feat: добавить подсчёт суммы заказов за неделю" 
```


<h3>GitHub-стиль</h3>
<p>GitHub можно использовать не только для хранения файлов проекта, но и для ведения списка задач (англ. issue) этого проекта. Если коммит «закрывает» или «решает» какую-то задачу, то в его сообщении удобно указывать ссылку на неё. Для этого в любом месте сообщения нужно указать #<номер задачи>. Например, вот так.
</p>

``` bash
git commit -m "Исправить #334, добавить график температуры" 
```

<h3>Игнорирование файлов</h3>
<p>Создаем файл .gitignore коммандой (в Windows)</p>

``` bash
New-Item .gitignore 
```

<p>В Линукс</p>

``` bash
touch .gitignore 
```

<p>Добавление каталога в файле .gitignore прописать как bin/</p>

<hr>
<h3>Нужно откатить изменения</h3>
<p>Команда уберёт файл credentials из списка на коммит, и он вернётся в состояние  untracked</p>

``` bash
git restore --staged credentials
```

<p>Команда откатит файл до состояния последней сохранённой в коммите версии app.js</p>

``` bash
git restore app.js
```


<p>Команда откатит состояние репозитория к предпоследнему коммиту. Последний коммит (aaa2508) при этом исчезнет из истории</p>

  ``` bash
git reset --hard 96aa6ee
```




