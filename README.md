# VK-Internship-task1

Реализованная программа предстваляет собой скрипт на языке Python 3. Перед использованием требуется установить игру Goose Goose Duck.

# Функционал

1) По приложенной ссылке скачивает файл в директорию игры;
2) Вносит значения из файла в реестр Windows;
3) Запускает Steam или игру.

# Сложности, с которыми столкнулся

Просто так скачать файл по ссылке не получится. При переходе по ссылке появляется страничка с предупреждением, что файл является исполняемым и может нанести вред вашему компьютеру. Если этот момент проигнорировать и скачать файл обычным способом, а именно через библиотеку requests, то у нас установится не требуемый файл с настройками, а файл, содержащий html код страницы с предпреждением.
Я заметил это не сразу, но когда всё таки понял ошибку выделил следующие способы решения проблемы:
1) Воспользоваться библиотекой selenium. Она позволяет управлять веб-браузером из кода на Python. С помощью selenium можно открыть страницу, найти кнопку "Скачать", а затем нажать ее, чтобы запустить процесс загрузки;
2) Использовать библиотеку gdown. Она позволяет загрузить файл из Google Drive по его ID.

Второй способ показался мне более логичным и простым, поэтому я решил воспользоваться им. Для этого я просто разбил строку, которая содержала ссылку по "id=" и взял её вторую половую, которая и содержала сам ID. Ну и наконец, воспользовался методом из библиотеки gdown для установки.

Еще одна проблема, с которой я столкнулся - невозможность внесения настроек в регистр. Здесь всё оказалось проще, нужно было указать нужную кодировку при занесении настроек, а именно utf-16.