# Инструкция по работе с git

## Что такое git

**Git** - это одна из реализаций системы контроля версий, поддерживающие как локальные, так и удаленные репозитории.
Самая популярная реализация Git - это [GitHub](https://github.com)

## Подготовка репозитория

Для создания репозитоория используется соманда **git init**.

## Что такое commit

**commit** - снимок текущего состояния изменений, добавленных в раздел проиндексированных файлов. Такие подтвержденные снимки состояния можно рассматривать как контрольные точки проекта — Git не будет их менять, пока вы явным образом не попросите об этом. Перед выполнением команды **git commit** необходимо использовать команду **git add**, чтобы добавить в проект изменения, которые будут сохранены в коммите.

## Перемещение между комитами

Для перемещения к определенному комиту надо использовать команду **git checkout _SHA_нужного_комита**. Чтобв найти SHA, надо воспользоваться командой **git log**.

## Создание веток репозитория

Для создания новой ветки репозитория необходимо использовать команду **git branch _имя_новой_ветки_**.
Для перемещения между ветками репозитория нужно использовать команду **git checkout _имя_ветки_репозитория_** или **git switch**.

## Слияние веток

Для слияния веток репозитория используется команда **git merge _имя_ветки_которую_необходимо_слить_с_текущей_**. Перед выполнением этой команды необходимо убедиться, что вы находитесь на принимающей веткке, в нашем случае это ветка master. Это делается командой **git status**. При необходимости надо перейти на принимающую ветку командой **git checkout master** или **git switch master**. При слиянии веток могут возникнуть конфликты. Для разрешения конфликтов необходимо использовать команды **git status** и **git diff** - эта команда показывает раницу между репозиториями.

## Журнал изменений

Для просмотра журнала изменений необходимо использовать **git log**  
Так же команду git log можно использовать с различными ключами, например:
**git log --oneline --decorate --all --graph** - показать все комиты и ветки репозитория в формате диаграммы.

# Удаленный репозиторий

Удаленный оепозиторий - это репозиторий, расположенный не на локальном компьютере, а где-то на сервере, либо в облаке, либо на специальных ресурсах, например GitHub.

## Создание удаленного репозитория

Репозиторий мы будем создавать на сервисе Github, для чего нам потребуется там зарегистрироваться и войти под полученным аккаунтом:

[Account Github](account_github.png)

Затем в правом верхнем углу надо нажать на кнопку **"+"** и выбрать New repository:

[Create repository](Create_repository.png)

Создаваемый репозиторий должен быть public, имя репозитория должно содержать латинские буквы и не содержать специальных символов, остальное оставить по умолчанию, после чего нажать на зеленую кнопку **Create repository**.

После этого Giyhub сгенерирует краткую инструкцию по применению созданного репозитория для синхронизации его с репозиторием локальным:

[Инструкция](inst_rep.png)

## Модели совместной разработки

### For + Pull
Эта модель позволяет любому сделать копию существующего репозитория (fork) в свой личный репозиторий и работать с ним без необходимости доступа к оригинальному репозиторию. Для внесения сделанных изменений в оригинальный репозиторий необходимо сделать *pull request*, т.е. отправить запрос хозяину оригинального репозитория на внесение изменений.

### The Shared Repository Model
Эта модель подразумевает наличие полного доступа к оригинальному репозиторию у всех разработчиков проекта. Для изолирования изменений применятся создание теметических веток (*topic branches*).


