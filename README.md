# REST API Boilerplate

![API Boilerplate Banner](assets/banner2.png)

A versatile API development boilerplate built with Django REST Framework, featuring Swagger UI documentation and a sample Teacher-Student relationship model. This project serves as a foundation for building robust RESTful APIs quickly.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Technologies](#technologies)
- [Setup Instructions](#setup-instructions)
- [API Usage](#api-usage)
- [Database Structure](#database-structure)
- [Project Structure](#project-structure)
- [Customization Guide](#customization-guide)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

This boilerplate provides a solid foundation for developing RESTful APIs using Django REST Framework. It demonstrates a One-to-Many relationship between Teachers and Students, but is designed to be easily customizable for any domain-specific API requirements.

Use this project as a starting point to:
- Quickly prototype APIs with proper documentation
- Learn best practices for structuring Django REST Framework projects
- Build upon a working example with proper models, serializers, and viewsets

## Features

- ✅ Complete CRUD operations for sample models
- ✅ RESTful API architecture
- ✅ Comprehensive API documentation with Swagger UI
- ✅ Relational database integration (SQLite by default, PostgreSQL ready)
- ✅ Organized project structure following best practices
- ✅ Automatic API endpoint discovery and routing
- ✅ JWT authentication framework ready (forthcoming)
- ✅ Test structure (forthcoming)

## Technologies

The core technologies used in this boilerplate:

- **Python 3.8+**: Core programming language
- **Django 4.2+**: Web framework
- **Django REST Framework 3.15+**: REST API development toolkit
- **drf-yasg**: Swagger UI integration for API documentation
- **SQLite/PostgreSQL**: Database systems

## Setup Instructions

1.  **Clone the Repository:**
    ```bash
    git clone <repository_url>
    cd <project_folder>
    ```

2.  **Create and Activate Virtual Environment:**
    *   Windows (PowerShell or CMD):
        ```bash
        python -m venv venv
        .\venv\Scripts\activate
        ```
    *   Linux / macOS:
        ```bash
        python -m venv venv
        source venv/bin/activate
        ```

3.  **Install Required Packages:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Apply Database Migrations:**
    ```bash
    python manage.py makemigrations api
    python manage.py migrate
    ```

5.  **Start Development Server:**
    ```bash
    python manage.py runserver
    ```

For more detailed setup instructions, refer to [doc/README.md](doc/README.md).

## API Usage

### API Endpoints:

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET    | /api/teachers/ | List all teachers |
| POST   | /api/teachers/ | Create a new teacher |
| GET    | /api/teachers/{id}/ | Retrieve teacher by ID |
| PUT    | /api/teachers/{id}/ | Update teacher by ID |
| DELETE | /api/teachers/{id}/ | Delete teacher by ID |
| GET    | /api/students/ | List all students |
| POST   | /api/students/ | Create a new student |
| GET    | /api/students/{id}/ | Retrieve student by ID |
| PUT    | /api/students/{id}/ | Update student by ID |
| DELETE | /api/students/{id}/ | Delete student by ID |

### Documentation:

* Swagger UI: [http://127.0.0.1:8000/swagger/](http://127.0.0.1:8000/swagger/)
* ReDoc: [http://127.0.0.1:8000/redoc/](http://127.0.0.1:8000/redoc/)

## Database Structure

The project includes two sample models to demonstrate relationships:

1. **Teacher**:
   - id: Primary Key
   - name: Character Field (max length 100)

2. **Student**:
   - id: Primary Key
   - name: Character Field (max length 100)
   - teacher: Foreign Key (references Teacher model)

This structure showcases a One-to-Many relationship where each student is associated with one teacher, but a teacher can have many students.

## Project Structure

```
project_root/
│
├── api/                    # API application
│   ├── migrations/         # Database migration files
│   ├── __init__.py
│   ├── admin.py            # Django admin configuration
│   ├── apps.py             # Application configuration
│   ├── models.py           # Data models
│   ├── serializers.py      # DRF serializers
│   ├── tests.py            # Test files
│   ├── urls.py             # API endpoint definitions
│   └── views.py            # API viewsets
│
├── school_project/         # Main project module
│   ├── __init__.py
│   ├── asgi.py             # ASGI configuration
│   ├── settings.py         # Project settings
│   ├── urls.py             # Main URL configuration
│   └── wsgi.py             # WSGI configuration
│
├── assets/                 # Static assets
│   └── banner.png          # Project banner image
│
├── doc/                    # Documentation
│   └── README.md           # Detailed setup instructions
│
├── .gitignore              # Git ignore file
├── manage.py               # Django management command
├── README.md               # This file
└── requirements.txt        # Package dependencies
```

## Customization Guide

To adapt this boilerplate for your own project:

1. **Rename the Project** (Optional):
   ```bash
   python manage.py rename_project new_project_name
   ```

2. **Modify Models**:
   - Edit `api/models.py` to define your own data models
   - Run migrations after changes: 
     ```bash
     python manage.py makemigrations
     python manage.py migrate
     ```

3. **Create Serializers**:
   - Update `api/serializers.py` to match your models

4. **Configure ViewSets**:
   - Modify `api/views.py` to define your API logic
   - Update `api/urls.py` to register your viewsets

5. **Customize Settings**:
   - Adjust database settings in `school_project/settings.py`
   - Configure authentication if needed

6. **Document Your API**:
   - Update the Swagger schema information in `school_project/urls.py`

## Contributing

To contribute to this project:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. 