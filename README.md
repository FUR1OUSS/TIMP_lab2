**Лабораторная работа 2**

**PART I**

1. Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).

**Создал пустой репозиторий с названием TIMP_lab2**

2. Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.

**git init**

**echo "test" >> README.md**

**git add README.md**

**git commit -m "test"**

**git branch -M main**

**git remote add origin https://github.com/FUR1OUSS/TIMP_lab2.git**

**git push -u origin main**

3. Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;.

**Создадим файл > hello_world.cpp и с помощью редактора nano реализуем код**

nano hello_world.cpp

<img width="682" alt="Снимок экрана 2023-05-18 в 17 21 40" src="https://github.com/FUR1OUSS/TIMP_lab2/assets/82472327/dd8a27f7-14dc-4712-83e2-40568aaedff7">

4. Добавьте этот файл в локальную копию репозитория.

**git add hello_world.cpp**

5. Закоммитьте изменения с осмысленным сообщением.

**git commit -m "bad style code"

6. Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя.

**Откроем код через редактор nano и внесем изменения**

nano hello_world.cpp

7. Закоммитьте новую версию программы. Почему не надо добавлять файл повторно git add?

**git commit -m "code style with string"**

8. Запуште изменения в удалёный репозиторий.

**git push -f origin main**

9. Проверьте, что история коммитов доступна в удалёный репозитории.

**git log**

<img width="682" alt="Снимок экрана 2023-05-18 в 18 04 14" src="https://github.com/FUR1OUSS/TIMP_lab2/assets/82472327/a126de4c-3250-4ba6-9e4c-0f75f4f6e4cd">

**PART II**

1. В локальной копии репозитория создайте локальную ветку patch1:

**git branch patch1**

2. Внесите изменения в ветке patch1 по исправлению кода и избавления от using namespace std;:

**Перейдем в ветку patch1 и с помощью редактора nano поменяем код**

git checkout patch1

nano hello_world.cpp

<img width="682" alt="Снимок экрана 2023-05-18 в 18 12 09" src="https://github.com/FUR1OUSS/TIMP_lab2/assets/82472327/9d85f541-586f-4d94-b66f-1ebcda8eba5c">

3. commit, push локальную ветку в удалённый репозиторий:

**git add . | git commit -m "code without namespace" | git push origin patch1**

4. Проверьте, что ветка patch1 доступна в удалёный репозитории:

git branch

<img width="682" alt="Снимок экрана 2023-05-18 в 18 32 44" src="https://github.com/FUR1OUSS/TIMP_lab2/assets/82472327/0bf6a5e5-ee4a-42fb-8b71-ddddae241b36">

5. Создайте pull-request patch1 -> master:

**Создал pull request**

<img width="595" alt="Снимок экрана 2023-05-18 в 18 36 01" src="https://github.com/FUR1OUSS/TIMP_lab2/assets/82472327/fb8881bf-3b47-44e9-ab69-94a194890947">

6. В локальной копии в ветке patch1 добавьте в исходный код комментарии:

**Откроем файл через редактор nano и добавим коментарии**

7. commit, push:

**git add . | git commit -m "code with //" | git push origin patch1

8. Проверьте, что новые изменения есть в созданном на шаге 5 pull-request:

<img width="864" alt="Снимок экрана 2023-05-18 в 18 47 01" src="https://github.com/FUR1OUSS/TIMP_lab2/assets/82472327/a947ceee-91de-47cb-8a64-4987e7466867">

9. В удалённый репозитории выполните слияние PR patch1 -> master и удалите ветку patch1 в удаленном репозитории:

**git merge patch1**

<img width="622" alt="Снимок экрана 2023-05-18 в 18 48 53" src="https://github.com/FUR1OUSS/TIMP_lab2/assets/82472327/63974553-a077-4c02-b79c-53704d2a6f3c">

10. Удалите локальную ветку patch1:

**git branch -d patch1**

**PART III**

1. Создайте новую локальную ветку patch2:

**git branch patch2**

2. Измените code style с помощью утилиты clang-format. Например, используя опцию -style=Mozilla:

**sudo apt install clang-format**

**clang-format -style="Mozilla" hello_world.cpp**
