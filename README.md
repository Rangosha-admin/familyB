# Семейный бюджет — запуск на Render

Приложение — статический сайт (без сервера), поэтому на Render это бесплатный Static Site с https, а значит его можно установить на телефон и рабочий стол.

## 1. Выложить на Render
1. Создайте репозиторий на GitHub и загрузите в его корень все файлы из этой папки (index.html, manifest.json, sw.js, иконки, render.yaml).
2. На render.com: New → Static Site → выберите репозиторий.
   (Или New → Blueprint: Render сам прочитает render.yaml.)
3. Build Command: `echo "static site"`, Publish Directory: `.`
4. Нажмите Deploy и откройте адрес вида https://family-budget.onrender.com

## 2. Установить как приложение
Chrome / Edge: значок установки в адресной строке. iPhone: «Поделиться → На экран Домой».

## 3. Включить синхронизацию между устройствами
1. console.firebase.google.com → создайте проект → Build → Authentication → включите «Anonymous».
2. Build → Firestore Database → создайте базу, во вкладке Rules вставьте содержимое firestore.rules.
3. Project settings → Your apps → Web → скопируйте объект firebaseConfig (в формате JSON).
4. В приложении нажмите на статус вверху → вставьте config и придумайте длинный семейный код. Повторите на каждом устройстве с тем же кодом.

Без синхронизации данные хранятся только в браузере устройства; копию можно скачать в том же окне.
