erDiagram
       USER ||--o{ TASK : creates
       USER {
           int id PK
           string username
           string email
           string password_hash
       }
       TASK {
           int id PK
           int user_id FK
           string title
           string description
           date due_date
           enum priority
           boolean is_complete
       }
       CATEGORY ||--o{ TASK : categorizes
       CATEGORY {
           int id PK
           string name
       }

### Task Manager API Endpoints
User Management

POST /api/users/register/
POST /api/users/login/
POST /api/users/logout/
POST /api/users/reset-password/

Tasks

GET /api/tasks/
POST /api/tasks/
GET /api/tasks/{id}/
PUT /api/tasks/{id}/
DELETE /api/tasks/{id}/

Categories

GET /api/categories/
POST /api/categories/
GET /api/categories/{id}/
PUT /api/categories/{id}/
DELETE /api/categories/{id}/

Project Structure

```
   task_manager/
   ├── manage.py
   ├── task_manager/
   │   ├── __init__.py
   │   ├── settings.py
   │   ├── urls.py
   │   └── wsgi.py
   ├── tasks/
   │   ├── migrations/
   │   ├── __init__.py
   │   ├── admin.py
   │   ├── apps.py
   │   ├── models.py
   │   ├── serializers.py
   │   ├── tests.py
   │   ├── urls.py
   │   └── views.py
   ├── users/
   │   ├── migrations/
   │   ├── __init__.py
   │   ├── admin.py
   │   ├── apps.py
   │   ├── models.py
   │   ├── serializers.py
   │   ├── tests.py
   │   ├── urls.py
   │   └── views.py
   ├── frontend/
   │   ├── static/
   │   │   ├── css/
   │   │   └── js/
   │   └── templates/
   └── requirements.txt
   ```
