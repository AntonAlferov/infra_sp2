#Учебный проект YaMDb

#Описание
Проект YaMDb собирает отзывы (Review) пользователей на произведения (Titles). Произведения делятся на категории (Category)
Список категорий  может быть расширен администратором.
Сами произведения в YaMDb не хранятся.
Произведению может быть присвоен жанр (Genre) из списка предустановленных. Новые жанры может создавать только администратор.
Пользователи могут оставить к произведениям текстовые отзывы (Review) и ставят произведению оценку в диапазоне от одного до десяти (целое число);
из пользовательских оценок формируется усреднённая оценка произведения — рейтинг(Rating) (целое число).
На одно произведение пользователь может оставить только один отзыв.

#Технологии
Python 3.7
Django 2.2.16
Django REST 3.12.4

#Как запустить проект:
Клонировать репозиторий и перейти в него в командной строке:

git clone https://github.com/AntonAlferov/api_final_yatube.git
cd api_final_yatube
Cоздать и активировать виртуальное окружение:

python3 -m venv venv
source venv/bin/activate
Установить зависимости из файла requirements.txt:

python3 -m pip install --upgrade pip
pip install -r requirements.txt
Выполнить миграции:

python3 manage.py migrate
Запустить проект:

python3 manage.py runserver

#Запуск с помощью Doker
#Описание команд для запуска приложения в контейнерах:
Установить Doker:
Вся информация по установке Doker на сайте https://docs.docker.com/
Через консоль перейти в каталог приложения infra:
cd infra/
Собрать и запустить все сервисы командой:
docker-compose up -d
Подготовить и запустить миграции:
docker-compose exec web python manage.py makemigrations
docker-compose exec web python manage.py migrate
Создать администратора:
docker-compose exec web python manage.py createsuperuser
Готово!
Сайт запущен по адресу localhost в адресной строке браузера
Ознакомиться с пользовательскими командами можно по ссылке localhost\redoc\
Остановить сервисы можно командой:
docker-compose stop

