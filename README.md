
# Django Multi-Database Tutorial

This repository provides a comprehensive guide on how to set up and use multiple databases within a single Django project. The tutorial demonstrates configuring PostgreSQL, MySQL, and SQLite3, and shows how to control where data is stored using Django's database routing capabilities.

## 🌟 Features
- Configure multiple databases in Django (`PostgreSQL`, `MySQL`, and `SQLite3`)
- Use database routers to control read and write operations
- Store and retrieve data from specific databases through views
- Step-by-step setup instructions with code examples

## 📋 Prerequisites
Before starting, make sure you have the following installed:
- Python 3.x
- Django
- PostgreSQL
- MySQL
- SQLite3
- Required database drivers:
  - `psycopg2-binary` for PostgreSQL
  - `mysqlclient` for MySQL

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/donaldte/django-multi-database-tutorial.git
cd django-multi-database-tutorial
```

### 2. Install Required Packages
```bash
pip install django psycopg2-binary mysqlclient
```

### 3. Configure the Databases
Edit the `settings.py` file to include the database configurations:
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    },
    'postgres': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'your_postgres_db',
        'USER': 'your_postgres_user',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '5432',
    },
    'mysql': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'your_mysql_db',
        'USER': 'your_mysql_user',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

### 4. Set Up Database Router
Create a file named `dbrouters.py` to control which database handles specific operations.

### 5. Apply Migrations
```bash
python manage.py migrate --database=postgres
python manage.py migrate --database=mysql
python manage.py migrate --database=default
```

### 6. Run the Application
```bash
python manage.py runserver
```

## 📂 Project Structure
```
django-multi-database-tutorial/
│
├── myapp/
│   ├── models.py
│   ├── views.py
│   ├── dbrouters.py
│   └── ...
│
├── django_multi_database/
│   ├── settings.py
│   └── ...
│
└── README.md
```

## 📝 Tutorial Explanation
For detailed instructions on how this setup works and code explanations, refer to the full tutorial in the `tutorial.md` file.

## 💡 Why Use Multiple Databases?
- **Performance Optimization**: Each database can handle specific workloads better, leading to performance improvements.
- **Data Segregation**: Segregate different types of data into separate databases for better organization.
- **Scalability**: Distribute your data load across multiple databases to scale more efficiently.
- **Legacy Integration**: Easily connect to and interact with legacy systems without data migration.

## 🤝 Contributing
Contributions are welcome! Please fork the repository and create a pull request with your improvements.

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ✨ Acknowledgements
Thanks to all the developers and contributors who made this project possible.

---
Feel free to reach out if you have any questions or suggestions. Happy coding!
```

