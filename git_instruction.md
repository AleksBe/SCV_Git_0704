![Logo Git](Logogit.jpg)
# Работа с Git
## 1. Проверка наличия установленного Git
В терминале выполнить команду:
`git version`
Если Git установлен, появится сообщение о версии программы. Иначе будет сообщение об ошибке.
## 2. Установка Git
Загружаем последнюю версию **Git** с сайта
Устанавливаем с настройками по умолчанию

## 3. Настройка Git
При первом использовании **Git** необходимо представиться. Для этого нужно ввести в терминале 2 команды:
```
git config --global user.name "Ваше имя"
git config --global user.email ваша почта.
```
## 4. Инициализация репозитория
В терминале переходим к папке, в которой хотим создать репозиторий. Выполняем команду `git init`
В исходной папке появится скрытая папка *.git*

## 5. Отслеживание репозитория

Чтобы посмотреть список новых или измененных файлов, которые ещё не закомитены, в терминале необходимо ввести команду `git status`.

## 6. Добавление файла к отслеживанию/добавление изменений в файл

Для того, чтобы добавить файл к отслеживанию программой **Git** а также, чтобы зафиксировать изменения в уже отслеживаемом файле, в терминале необходимо ввести команду `git add имя файла`.
Эта команда является многофункциональной, она используется для добавления под версионный контроль новых файлов, для индексации изменений (подготовки к записи изменений) и других целей.

## 7. Добавление коммитов (фиксация изменений файла)

Для того, чтобы зафиксировать изменения, и понимать впоследствии какие конкретно изменения были внесены, в терминале необходимо ввести команду `git commit -m "Текст коммита - описание сделанных в файле изменений".

## 8. Просмотр изменений файла, которые еще не зафиксированы

Для того, чтобы просмотреть разницу между текущим файлом и последним коммитом необходимо ввести команду `git diff`.

## 9. Просмотр истории изменений (коммитов)

Для того, чтобы посмотреть историю изменений файла (коммитов), в терминале необходимо ввести команду `git log`.
Данная команда перечисляет коммиты с их хеш-кодами, именем и электронной почтой автора, датой создания и сообщения коммита.

Для выхода из режима просмотра истории используется клавиша `q`

## 10. Перемещения между сохранениями

Для того, чтобы перейти к какому-то конкретному коммиту необходимо в терминале ввести команду `git checkout хеш код коммита`. Хеш-код соответствующего коммита можно увидеть в журнале изменений, вызываемом командой `git log`.
По умолчанию последние коммиты находятся вверху. Чтобы вернуться к последней версии файла необходимо набрать команду `git checkout master`.

## 11. Игнорирование файлов

Для того чтобы исключить из отслеживания в репозитории определенные файлы или папки необходимо создать там файл ***.gitignore*** и записать в него их названия или шаблоны, соответствующие таким файлам или папкам.


## 12. Создание веток в Git

Ветка в Git - простой перемещаемый указатель на один из коммитов, обычно последний в цепочке коммитов. 

Создать ветку можно командой
```
git branch имя новой ветки
```
В результате создается новый указатель на текущий коммит. Список веток в репозитории можно посмотреть с помощью команды `git branch`.

Для переключения между ветками используется команда `git checkout имя ветки`.

## 13. Слияние веток и разрешение конфликтов

Для слияния выбранной ветки с текущей нужно выполнить команду:
```
git merge название выбранной ветки (с которой сливаемся)
```
Если была изменена одна и та же часть файла в обеих ветках, то может возникнуть конфликт, который потребует участия пользователя (нужно будет выбрать что делать).

## 14. Удаление веток

После выполнения слияния ненужную ветку можно удалить командой `git branch -d название ветки`.
Если ветка, которую мы хотим удалить, содержит ещё не слитые в основную ветку наработки, попытка удалить её вышеприведенной командой приведет к ошибке.

Чтобы удалить верку со всеми наработками, следует использовать команду:
```
git branch -D название ветки
```
## 15. Работа с удаленными репозиториями

Для работы с удаленными репозиториями можно использовать веб-сервис `GitHub`. Чтобы начать работу, необходимо создать учетную запись. Необходимо зайти на `https://github.com`, выбрать имя, которое еще не занято, указать адрес электронной почты и пароль.

Чтобы скопировать (клонировать) удаленный репозиторий на свой локальный компьютер необходимо выполнить следующие действия:

* Найти нужный репозиторий на `GitHub`, для чего можно воспользоваться поиском;

* Скопировать ссылку на данный репозиторий (можно найти под кнопкой **Code**);

* На терминале локального компьютера выполнить команду
```
git clone ссылка на удаленный репозиторий, которую мы скопировали
```

Чтобы отправить репозиторий с локального компьютера на сервис `GitHub` необходимо выполнить следующие действия:

* Создать удаленный репозиторий на `GitHub` и дать ему имя;

* Скопировать ссылку на данный репозиторий (можно найти по кнопкой **Code**);

* На терминале локального компьютера последовательно выполнить следующие команды:

```
git remote add origin ссылка на созданный репозиторий
git branch -M main
git push -u origin main
```
При первой попытке отправить данный на удаленный сервер программа предложит авторизоваться.

Впоследствии, можно работать с данным репозиторием на локальном компьютере, вносить в него изменения, делать коммиты. Чтобы отправить данные изменения на `GitHub`, необходимо на терминале локального компьютера выполнить команду
```
git push
```
Для того, чтобы скачать последнюю версию репозитория с `GitHub` (актуально когда над проектом работает несколько пользователей, каждый из которых может вносить изменения в репозиторий) необходимо на терминале локального компьютера выполнить команду
```
git pull
```
Помимо переноса данных, данная команда автоматически соединит ветки файла с локального репозитория и переносимого файла.

Для того, чтобы предложить свои изменения владельцу удаленного репозитория, при отсутствии прав вносить эти изменения самостоятельно на `GitHub` можно воспользоваться функционалом **Pull Request** для этого необходимо выполнить следующие действия:

* Сделать `fork` интересующего нас репозитория (при этом репозиторий загрузится на наш аккаунт `GitHub`);
* Клонировать репозиторий со **своего** аккаунта в `GitHub` на локальный компьютер с помощью команды
```
git clone ссылка на репозиторий
```
* На локальном компьютере создать новую ветку, в которую вносятся изменения, фиксируются, делаются коммиты;

* Отправить исправленную версию на свой аккаунт в `GitHub` с помощью команды
```
git push
```
* На сервисе `GitHub` нажать кнопку `PullRequest`, которая отправит изменения владельцу репозитория.
Ознакомившись с изменениями, владелец репозитория примет решение как с ними поступить.