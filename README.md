________________________________________________________________________________________________________________________
КРАТКОЕ ОПИСАНИЕ ПРИЛОЖЕНИЯ.
________________________________________________________________________________________________________________________
Программа создана для предоставления пользователю возможности прохождения полноценного теста на личность по системе Майерс-Бриггс.
При запуске приложения пользователя приветствует диалоговое окно с предложением ввести свое имя 
(если пользователь откажется это делать, то его именем автоматически станет ‘Anonymous’).
Далее нас ждет главное меню. Настоятельно рекомендую ознакомиться со вступлением, которая расскажет и покажет, что к чему. 
Есть возможность изменить имя и язык(пока присутствует лишь два: английский и русский). 
Текст в диалоговых окнах также зависит от языка. При нажатии кнопки “НАЧАТЬ” пользователь приступает к выполнению теста, состоящего из 36 вопросов.
Есть возможность вернуться к любому предыдущему вопросу и изменить свой ответ на один из четырех возможных вариантов. 
Для этого есть кнопки “Назад” и “Вперед”. Вы все еще можете сменить язык, а внизу показывается текущий номер вопроса. 
При попытке перейти к следующему вопросу, не выбрав один из вариантов, вылезает ошибка.
По окончании прохождения теста пользователь попадает на окно с результатами теста (детальное описание определенного типа личности и картинка).
Можно поменять язык и начать прохождение теста заново. Все вопросы, а также описания типов личности хранятся в специальной базе данных mbti.bd.
Были использованы библиотеки PyQt6, а также встроенные sqlite3, random и sys.
________________________________________________________________________________________________________________________
ИНСТРУКЦИЯ ПО ЗАПУСКУ
________________________________________________________________________________________________________________________
0. Убедитесь, что у вас установлен Python и git. 
1. Перейдите в папку, в которую вы хотите склонировать приватный репозиторий с помощью команды:

cd <путь_к_папке>

2. Склонируйте репозиторий на свой компьютер с помощью консольной команды:

git clone https://github.com/pr1kol2005/mbti_test.git --branch dev
(Вам может потребоваться ввести учетные данные для доступа к репозиторию.)

3. Перейдите в директорию с репозиторием:

cd mbti_test

4. Установите необходимые библиотеки, выполнив команду:

pip install -r requirements.txt

5. Теперь вы можете запустить файл main.py командой:

python3 main.py (если не работает, то python main.py)

6. Приложение должно успешно начать работу.

7. Чтобы запустить unit-test, пропишите следующее:

python3 unit_test.py (если не работает, то python unit_test.py)
________________________________________________________________________________________________________________________
РЕШЕНИЕ ПРОБЛЕМЫ, СВЯЗАННОЙ С PYQT6 НА MAC:
qt.qpa.plugin: Could not find the Qt platform plugin "cocoa" in ""
This application failed to start because no Qt platform plugin could be initialized. Reinstalling the application may fix this problem.

zsh: abort      python main.py
________________________________________________________________________________________________________________________
https://stackoverflow.com/questions/76898551/qt-qpa-plugin-could-not-find-the-qt-platform-plugin-cocoa-in
1. Найдите файл libqcocoa.dylib и его полный путь, например:
/Users/<user>/anaconda3/lib/python3.11/site-packages/PyQt6/Qt6/plugins/platforms

2. Обновите переменную QT_PLUGIN_PATH:

export QT_PLUGIN_PATH=/Users/<user>/anaconda3/lib/python3.11/site-packages/PyQt6/Qt6/plugins

3. Найдите файл qt.conf (в моем случае он находится в /Users/<user>/anaconda3/bin), откройте его и добавьте строку:

Plugins = /Users/<user>/anaconda3/lib/python3.11/site-packages/PyQt6/Qt6/plugins
________________________________________________________________________________________________________________________
