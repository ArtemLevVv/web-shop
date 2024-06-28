# web-shop

Проект підтримується та розвивається наступними учасниками команди:
  -
  -
  -


Проект "Інтернет Магазин" – це повнофункціональний веб-додаток для онлайн продажу товарів. Він включає 
авторизацію для користувачів та адміністраторів, управління товарами (додавання, редагування, видалення), 
відправку повідомлень про замовлення, інтеграцію з Telegram для отримання та редагування інформації про 
користувачів та товари.

## Чому проект корисний
Проект "Інтернет Магазин" корисний як для користувачів, так і для розробників:
- **Користувачі** швидко розбираються з інтерфейсом та функціоналом, отримують зручний інструмент для покупок.
- **Замовники** отримують впевненість в тому, що проект може бути реалізований на високому рівні.
- **Розробники** набувають практичних навичок, покращують алгоритмічне мислення, вчаться працювати в команді та
відповідально ставитися до своїх завдань.

## Для роботи проекту необхідно встановити наступні модулі:
- `aiofiles` 23.2.1 	– 	для роботи з файлами асинхронно.
- `aiogram` 3.8.0 	– 	для роботи з Telegram API.
- `aiohttp` 3.9.5 	– 	асинхронний HTTP-клієнт/сервер.
- `alembic` 1.13.1 	– 	для управління міграціями бази даних.
- `Flask` 3.0.3 	– 	мікрофреймворк для веб-додатків на Python.
- `Flask-Login` 0.6.3 	– 	для управління сесіями користувачів.
- `Flask-Mail` 0.10.0 	– 	для відправки електронних листів.
- `Flask-Migrate` 4.0.7 – 	для роботи з міграціями бази даних.
- `Flask-SQLAlchemy` 3.1.1 – 	ORM для Flask.
- `openpyxl` 3.1.2 	– 	для роботи з Excel файлами.
- `pandas` 2.2.2 	– 	для аналізу даних.
- `SQLAlchemy` 2.0.29 	– 	ORM для Python.

## Інструкція по запуску проекту
#### Локально

1. Клонуйте репозиторій:
git clone https://github.com/your-repository.git


2. Перейдіть до директорії проекту:
 ``` cd your-repository ```  

3. Встановіть необхідні модулі:
<code> pip install -r requirements.txt </code>

4Запустіть додаток:
<code> flask run </code>

#### Віддалено (pythonanywhere)
1.  Зареєструйтеся на pythonanywhere.com.
2.  Створіть новий веб-додаток, вибравши відповідні налаштування для Flask.
3.  Завантажте код вашого проекту на сервер (через Git або вручну).
4.  Встановіть необхідні модулі
    <code> pip install -r requirements.txt </code>
5.  Налаштуйте конфігураційні файли та запустіть веб-додаток.

## Приклад створення головного додатку які ви можете бачити в нащому проекті

### Shop_app
``` python
import flask 

# Blueprint for shop functionality / Блюпринт для функціоналу магазину
shop = flask.Blueprint(
    name = "shop",  # Name of the blueprint / Назва блупринта
    import_name = "app",  # Import name for the blueprint / Ім'я імпорту для блупринта
    template_folder = "shop_page/templates",  # Folder for shop templates / Папка для шаблонів магазину
    static_folder = "static/shop_page",  # Folder for shop static files / Папка для статичних файлів магазину
    static_url_path = "/shop/"  # URL path for shop static files / URL шлях для статичних файлів магазину
)

```
### reg_app / registration_app
``` python
import flask

# Blueprint for registration functionality / Блюпринт для функціоналу реєстрації
reg = flask.Blueprint(
    name = 'registration',  # Name of the blueprint / Назва блупринта
    import_name = "app",  # Import name for the blueprint / Ім'я імпорту для блупринта
    template_folder = "reg_page/templates",  # Folder for registration templates / Папка для шаблонів реєстрації
    static_folder = "static",  # Folder for registration static files / Папка для статичних файлів реєстрації
    static_url_path = "/reg"  # URL path for registration static files / URL шлях для статичних файлів реєстрації
)
```
### log_app/ login_app
``` python
import flask

# Blueprint for login functionality / Блюпринт для функціоналу входу
log = flask.Blueprint(
    name = "login_page",  # Name of the blueprint / Назва блупринта
    import_name = "app",  # Import name for the blueprint / Ім'я імпорту для блупринта
    template_folder = "log_page/templates",  # Folder for login templates / Папка для шаблонів входу
    static_folder = "static",  # Folder for login static files / Папка для статичних файлів входу
    static_url_path = "/log"  # URL path for login static files / URL шлях для статичних файлів входу
)
```
### home_app
``` python
import flask 

# Blueprint for home functionality / Блюпринт для функціоналу домашньої сторінки
home = flask.Blueprint(
    name = "home",  # Name of the blueprint / Назва блупринта
    import_name = "app",  # Import name for the blueprint / Ім'я імпорту для блупринта
    template_folder = "home_page/templates",  # Folder for home templates / Папка для шаблонів домашньої сторінки
    static_folder = "static/home_page",  # Folder for home static files / Папка для статичних файлів домашньої сторінки
    static_url_path = "/home/"  # URL path for home static files / URL шлях для статичних файлів домашньої сторінки
)
```
### basket_app
``` python
import flask 

# Blueprint for basket functionality / Блюпринт для функціоналу кошика
basket = flask.Blueprint(
    name = "basket",  # Name of the blueprint / Назва блупринта
    import_name = "basket_app",  # Import name for the blueprint / Ім'я імпорту для блупринта
    template_folder = "basket_page/templates",  # Folder for basket templates / Папка для шаблонів кошика
    static_folder = "static/basket_page",  # Folder for basket static files / Папка для статичних файлів кошика
    static_url_path = "/basket/"  # URL path for basket static files / URL шлях для статичних файлів кошика
)
```
### admin_app
``` python
import flask

# Blueprint for admin functionality / Блюпринт для функціоналу адміністратора
admin = flask.Blueprint(
    name = 'admin',  # Name of the blueprint / Назва блупринта
    import_name = 'admin_page',  # Import name for the blueprint / Ім'я імпорту для блупринта
    template_folder = 'templates',  # Folder for admin templates / Папка для шаблонів адміністратора
    static_folder= 'static',  # Folder for admin static files / Папка для статичних файлів адміністратора
    static_url_path= '/admin/'  # URL path for admin static files / URL шлях для статичних файлів адміністратора
)
```

