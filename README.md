# Hospital_managment_apis
# 🏥 Healthcare Backend API

A Django REST Framework backend project for managing a healthcare system, including authentication, patient and doctor management, and doctor-patient mappings.

---

## 🚀 Features

* 🔐 JWT Authentication (via `djangorestframework-simplejwt`)
* 👩‍⚕️ Doctor and 👨‍⚕️ Patient Management (CRUD)
* 🔗 Patient-Doctor Mapping System
* 📦 PostgreSQL Database
* ⚙️ Secure Configuration with `.env`

---

## 📁 Project Structure

```
healthcare_backend/
├── core/                  # Main app
│   ├── models.py          # Models for User, Patient, Doctor, Mapping
│   ├── serializers.py     # DRF serializers
│   ├── views.py           # API views
│   ├── urls.py            # App-level URLs
│   ├── admin.py           # Admin registrations
├── healthcare_backend/   # Project settings
│   ├── settings.py        # Settings with PostgreSQL and JWT config
│   ├── urls.py            # Project URL config
├── .env                  # Environment variables (not committed)
├── requirements.txt      # Project dependencies
├── manage.py             # Django management script
```

---

## 🔧 Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/healthcare_backend.git
cd healthcare_backend
```

### 2. Create a virtual environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure `.env`

Create a `.env` file in the root directory:

```env
SECRET_KEY=your-secret-key
DEBUG=True
DB_NAME=your_db_name
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_HOST=localhost
DB_PORT=5432
```

### 5. Apply migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Create superuser

```bash
python manage.py createsuperuser
```

### 7. Run the server

```bash
python manage.py runserver
```

---

## 📮 API Endpoints

### 🔐 Authentication

* `POST /api/auth/register/` – Register a user
* `POST /api/auth/login/` – Obtain JWT tokens
* `POST /api/auth/refresh/` – Refresh access token

### 👤 Patient APIs

* `POST /api/patients/`
* `GET /api/patients/`
* `GET /api/patients/<id>/`
* `PUT /api/patients/<id>/`
* `DELETE /api/patients/<id>/`

### 🩺 Doctor APIs

* `POST /api/doctors/`
* `GET /api/doctors/`
* `GET /api/doctors/<id>/`
* `PUT /api/doctors/<id>/`
* `DELETE /api/doctors/<id>/`

### 🔗 Mapping APIs

* `POST /api/mappings/`
* `GET /api/mappings/`
* `GET /api/mappings/<patient_id>/`
* `DELETE /api/mappings/<id>/`

---

## 🧪 Testing

Use Postman or any API client to test endpoints.

You can authenticate by including the JWT access token in the `Authorization` header:

```
Authorization: Bearer <your_token>
```

---

## 📌 License

This project is licensed under the MIT License. Feel free to use and modify it as needed.

---

## 🙌 Acknowledgements

* [Django](https://www.djangoproject.com/)
* [Django REST Framework](https://www.django-rest-framework.org/)
* [Simple JWT](https://django-rest-framework-simplejwt.readthedocs.io/en/latest/)
