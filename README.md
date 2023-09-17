pwd - показать текущую директорию

cd ~ - сменить на домашнюю директорию

ls - вывести содержимое директории

cd .. - вернуться в родительскую директорию (то есть на директорию выше)

cd . - перейти в текущую директорию

cd github/open-source-project # переходим через несколько директорий - в папку open-source-project

$ ls -a # вывели список, в котором отображаются скрытые файлы ., .. и .git

touch - создать файл ( $ touch my-new-file.txt # создали файл my-new-file.txt  )

mkdir - создать директорию

mkdir -p - создать структуру директорий (например, mkdir -p dir1/dir-inside/dir-deeper-inside)

mkdir ~/my-git-projects - создать внутри домашней траектории папку

touch ../../file.txt

А команда touch ../../file.txt создаст файл file.txt на две папки выше по иерархии

cp - копировать файлы - $ cp index.html src/ # скопировали index.html в папку src 

mv - переместить фcd

$ mv table.csv ./very-important-files

# сначала указываем имя файла, который хотим переместить, потом путь — куда перемещаем 

cat - чтение файлов (работает только с текстовыми файлами)

rm test.txt - удалить файл test.txt

rmdir - удалить папку (работает только если папка пустая)

rm -r images - удалить папку images # удалили папку images со всем её содержимым из текущей директории

cd /c - перейти в корневую директорию


$ git config --global user.name "User Namovich" 
# имя или ник нужно написать латиницей и в кавычках

$ git config --global user.email username@yandex.ru
# здесь нужно указать свой настоящий email




$ cat ~/.gitconfig - Все глобальные настройки Git хранит в файле .gitconfig в домашней директории. Команда запишет в этот файл указанные имя и почту. Чтобы убедиться в этом, можно вызвать команду для чтения файлов.

$ git config --list - Другой способ проверки — вывести содержимое файла конфигурации Git той же командой git config с флагом --list (англ. «список»).



git init - создать репозиторий




Разгитить» папку, если что-то пошло не так, — rm -rf .git


Чтобы запомнить новое состояние файла, нужно снова ввести команду git add и передать в качестве параметра имя изменённого файла или ключ --all.

$ git add todo.txt

# или

$ git add --all


Команда git add позволяет подготовить файл к сохранению.
Команда git add --all подготовит к сохранению сразу все файлы.
С помощью git add . можно добавить в репозиторий текущую папку со всеми файлами.



ls -a ~/.ssh - показать содержимое папки .ssh
ls -la ~/.ssh - эта команда покажет содержимое папки .ssh в виде списка файлов



Как добавлять изменения файла на гитхаб (коммиты)?
сначала изменяем файл, потом гит адд, потом гит коммит, потом гит пуш




Хеш — основной идентификатор коммита и позволяет узнать его автора, дату и содержимое закоммиченных файлов.

Можно вызвать не только полный лог, но и сокращённый — это делается командой git log --oneline

В числе прочих файлов в папке .git есть служебный файл HEAD. Он указывает на самый свежий коммит.

Статусом untracked помечается файл, о существовании которого Git знает, но не следит за изменениями в нём. Этот статус — противоположность tracked, в который попадают все файлы, отслеживаемые Git.
Файл переходит в статус staged после выполнения git add.
Статус modified означает, что файл был изменён.
Большинство файлов в проектах «шагает» по следующему циклу: «изменён» → «добавлен в список на коммит» → «закоммичен» → «изменён» → и так далее.

Команда git status всегда подскажет, что происходит с файлом: например, он добавлен в список «на коммит» или ещё вообще не отслеживается, или изменён.
git status показывает явно следующие состояния файлов: untracked, staged и modified.
git status подсказывает, какие команды можно выполнить, чтобы поменять состояние файла.


example

HEAD -- это голова.
Коммит -- это всему голова.
Статусы файлов:
<тут пустая строка!>

```mermaid
%% описание схемы
```
<и тут пустая строка!> 





HEAD -- это голова.
Коммит -- это всему голова.
Статусы файлов:
<тут пустая строка!>


```mermaid
graph TD;
	A[untracked (неотслеживаемый)] -- git add --> B[staged (в списке на коммит) + tracked]
	B -- git commit --> C[tracked (отслеживаемый)]
	C -- Изменения --> D[modified (изменённый)]
	D -- git add --> B
	B -- Изменения --> D
```




```mermaid
graph LR;
  untracked -- "git add" --> "staged + tracked";
  "staged + tracked" -- "git commit" --> tracked;
  

%% стрелка без текста для примера: 
  A --> B;
```



