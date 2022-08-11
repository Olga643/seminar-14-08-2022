# Инструкция по работе с GIT

## Что такое GIT

Git - одна из реализаций распределенных систем контроля версий, позволяющая организовать версионность как локально, так и на удаленном сервере. Самая популярная форма, реализующая *GIT* -[GitHub] (http://github.com)

## Подготовка репозитория

Для создания в папке репозитория необходимо открыть эту папку в терминале и написать команду git init, после чего в этой папке создастся скрытая папка .git. Таким образом папка станет репозиторием.

## Создание коммитов
### Просмотр состояния репозитория

Для просмотра состояния репозитория используется команда *git status*. В терминале с открытой папкой-репозиторием необходимо написать команду git status. В результате можно увидеть следующие выводы:
1. Nothing to commit - нет активных изменений
2. Untracked file - это означает, что имеются файлы неотслеживаемые системой контроля версий.
3. Changes to be commited - изменения сохранены, нужно сделать коммит
4. Changes not staged for commit - изменения не подготовлены для коммита, нужно сначала сохранить, потом сделать коммит.

### Добавление файла к коммиту

Для того, чтобы добавить файл к сохранению необходимо использовать команду *git add*. В терминале с открытой папкой-репозиторием необходимо написать *git add* (название файла), и этот файл добавитс к "сохранению".

### Создание фиксации

Для создания фиксации используется команда *git commit*. Для этого в терминале папки с репозиторием необходимо писать команду *git commit -m "Сообщение к коммиту"*. Сообщение к коммиту писать **ОБЯЗАТЕЛЬНО**

## Журнал изменений

Для просмотра истории изменений используется команда *git log*. Для этого в терминале с папкой-репозиторием необходимо писать *git log* и будет выдан список всех коммитов в этой ветке с описанием имени, электронной почты, сообщением к коммиту и номер коммита.
## Перемещение между коммитами

Для перемещения между коммитами используется команда *git checkout*. Для этого в терминале с папкой-репозиторием необходимо написать *git checkout (номер коммита)*. Номер коммита берется из журнала изменений ветки

## Ветки GIT

Ветка представляет собой отдельное направление разработки. Ветки выступают в качестве абстрактного представления для процесса редактирования коммита. Новые коммиты записываются в историю текущей ветки, что приводит к образованию развилки в истории проекта.
Ветки создаются с помощью команды *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch* (название ветки), затем с помощью команды *git checkout* (назнание ветки) перейти на нее.
## Слияние веток и решение конфликтов

Для слияния веток используется команда *git merge*. В первую очередь необходимо в помощью команды *git checkout* встать на принимающую ветку, затем набрать команду *git merge* (название ветки, которая будет объединена с принимающей).

При попытке объединить ветки, в которых изменена одна и та же часть того же файла, Git не сможет сделать выбор между версиями. В таком случае операция останавливается прямо перед созданием коммита слияния, чтобы пользователь вручную разрешил конфликты.

Когда Git обнаруживает конфликт в ходе слияния, к затронутым файлам добавляются визуальные индикаторы по обе стороны проблемного содержимого: <<<<<<<, ======= и >>>>>>>.

После обнаружения конфликтующих участков кода можно исправить их по своему усмотрению. Затем необходимо выполнить команду *git add* для конфликтующего файла или файлов — так Git узнает, что конфликт разрешен. Затем выполняется обычная команда *git commit -m*, чтобы создать коммит слияния.
## Удаление веток

Для удаления ветки после слияния используется команда *git branch -d*. Для этого в терминале с папкой-репозиторием необходимо написать команду *git branch -d (название удаляемой папки)*.