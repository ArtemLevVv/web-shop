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
### example/приклад
```python
import flask

example = flask.Bkueprint(
    name = 'name_of_Blueprint',
    import_name - 'name_of_file',
    template_folder = 'path_to_your_templates_folred',
    static_folder = 'path_to_your_templates_folred',
    static_url_path = 'url_path_sabe_with_url_in_url'
)
```

### project ursl
``` python
import home_page  # Import the home_page module / Імпортуємо модуль home_page
from .settings import project  # Import the project object from settings / Імпортуємо об'єкт project з налаштувань
import log_page  # Import the log_page module / Імпортуємо модуль log_page
import reg_page  # Import the reg_page module / Імпортуємо модуль reg_page
import shop_page  # Import the shop_page module / Імпортуємо модуль shop_page
import basket_page  # Import the basket_page module / Імпортуємо модуль basket_page
import admin_page  # Import the admin_page module / Імпортуємо модуль admin_page

# Add a URL rule for the home page / Додаємо правило URL для домашньої сторінки
# Mapping the root URL to the render_home function / Відповідність кореневого URL функції render_home
home_page.home.add_url_rule(rule="/", view_func=home_page.render_home)

# Add a URL rule for the shop page / Додаємо правило URL для сторінки магазину
# Mapping /shop/ to the render_shop function / Відповідність /shop/ функції render_shop
# Allowing both GET and POST methods / Дозволяємо методи GET та POST
shop_page.shop.add_url_rule(rule="/shop/", view_func=shop_page.render_shop, methods=['GET', 'POST'])

# Add a URL rule for the registration page / Додаємо правило URL для сторінки реєстрації
# Mapping /reg/ to the render_reg function / Відповідність /reg/ функції render_reg
# Allowing both GET and POST methods / Дозволяємо методи GET та POST
reg_page.reg.add_url_rule(rule='/reg/', view_func=reg_page.render_reg, methods=['GET', 'POST'])

# Add a URL rule for the login page / Додаємо правило URL для сторінки входу
# Mapping /log/ to the show_authorization function / Відповідність /log/ функції show_authorization
# Allowing both GET and POST methods / Дозволяємо методи GET та POST
log_page.log.add_url_rule(rule='/log/', view_func=log_page.show_authorization, methods=['GET', 'POST'])

# Add a URL rule for the basket page / Додаємо правило URL для сторінки кошика
# Mapping /cart/ to the render_basket function / Відповідність /cart/ функції render_basket
# Allowing both GET and POST methods / Дозволяємо методи GET та POST
basket_page.basket.add_url_rule(rule='/cart/', view_func=basket_page.render_basket, methods=['GET', 'POST'])

# Add a URL rule for the admin page / Додаємо правило URL для сторінки адміністратора
# Mapping /admin/ to the render_admin function / Відповідність /admin/ функції render_admin
# Allowing both GET and POST methods / Дозволяємо методи GET та POST
admin_page.admin.add_url_rule(rule='/admin/', view_func=admin_page.render_admin, methods=["GET", "POST"])

# Register the basket blueprint with the project / Реєструємо блупринт кошика з проектом
project.register_blueprint(blueprint=basket_page.basket)

# Register the home blueprint with the project / Реєструємо блупринт домашньої сторінки з проектом
project.register_blueprint(blueprint=home_page.home)

# Register the shop blueprint with the project / Реєструємо блупринт магазину з проектом
project.register_blueprint(blueprint=shop_page.shop)

# Register the registration blueprint with the project / Реєструємо блупринт реєстрації з проектом
project.register_blueprint(blueprint=reg_page.reg)

# Register the login blueprint with the project / Реєструємо блупринт входу з проектом
project.register_blueprint(blueprint=log_page.log)

# Register the admin blueprint with the project / Реєструємо блупринт адміністратора з проектом
project.register_blueprint(blueprint=admin_page.admin)
```

## Усі файли інші файли які в project

### project settings

``` python
import flask  # Import Flask framework / Імпортуємо Flask фреймворк
import flask_sqlalchemy  # Import SQLAlchemy for database management / Імпортуємо SQLAlchemy для керування базою даних
import flask_migrate  # Import Flask-Migrate for database migrations / Імпортуємо Flask-Migrate для міграцій бази даних
import os  # Import os module for operating system interactions / Імпортуємо модуль os для взаємодії з операційною системою

# Initialize Flask project / Ініціалізуємо Flask проект
project = flask.Flask(
    import_name="settings",  # Import name / Ім'я імпорту
    template_folder="project/templates",  # Folder for templates / Папка для шаблонів
    instance_path=os.path.abspath(__file__ + "/.."),  # Instance path / Шлях до інстансу
)

# Configure the database URI / Налаштовуємо URI бази даних
project.config["SQLALCHEMY_DATABASE_URI"] = "sqlite:///data.db"

# Initialize SQLAlchemy with the Flask project / Ініціалізуємо SQLAlchemy з Flask проектом
DATABASE = flask_sqlalchemy.SQLAlchemy(app=project)

# Initialize Flask-Migrate with the Flask project and database / Ініціалізуємо Flask-Migrate з Flask проектом і базою даних
migrate = flask_migrate.Migrate(app=project, db=DATABASE)



```

### project login_manager
``` python
import flask_login  # Import Flask-Login for user session management / Імпортуємо Flask-Login для керування сесіями користувачів

from .settings import project  # Import the Flask project from settings / Імпортуємо Flask проект з налаштувань
from reg_page.models import Users  # Import the Users model from reg_page.models / Імпортуємо модель Users з reg_page.models

# Set secret key for the project / Встановлюємо секретний ключ для проекту
project.secret_key = '200'

# Initialize LoginManager with the Flask project / Ініціалізуємо LoginManager з Flask проектом
login_manager = flask_login.LoginManager(project)

# Define user loader function for LoginManager / Визначаємо функцію завантажувача користувачів для LoginManager
@login_manager.user_loader
def load_user(id):
    return Users.query.get(id)  # Get user by ID / Отримати користувача за ID

```

### project mail_config 
``` python
import flask_mail  # Import Flask-Mail for email support / Імпортуємо Flask-Mail для підтримки електронної пошти
from project.settings import project  # Import the Flask project from settings / Імпортуємо Flask проект з налаштувань

# Define the Gmail address / Визначаємо адресу Gmail
gmail_address = "arzon.art125@gmail.com"

# Configure Flask-Mail settings / Налаштовуємо параметри Flask-Mail
project.config['MAIL_SERVER'] = 'smtp.gmail.com'  # Mail server / Поштовий сервер
project.config['MAIL_PORT'] = 587  # Mail port / Поштовий порт
project.config['MAIL_USE_TLS'] = True  # Use TLS / Використовувати TLS
project.config['MAIL_USE_SSL'] = False  # Use SSL / Використовувати SSL
project.config['MAIL_USERNAME'] = gmail_address  # Mail username / Ім'я користувача пошти
project.config['MAIL_PASSWORD'] = ''  # Mail password / Пароль до пошти

# Initialize Flask-Mail with the Flask project / Ініціалізуємо Flask-Mail з Flask проектом
mail = flask_mail.Mail(project)
```
