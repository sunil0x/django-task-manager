# Django Task Manager - CRUD Application with Authentication

A simple yet powerful task management web application built with Django. This project demonstrates full CRUD (Create, Read, Update, Delete) functionality with user authentication and authorization.

## 📋 Table of Contents

- [Features](#features)
- [Screenshots](#screenshots)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)

## ✨ Features

### Authentication System
- ✅ User Registration
- ✅ User Login
- ✅ User Logout
- ✅ Password validation
- ✅ Login required protection for task operations

### CRUD Operations
- ✅ **Create** - Add new tasks with title and description
- ✅ **Read** - View all your tasks in a clean table layout
- ✅ **Update** - Edit existing tasks and mark them as completed
- ✅ **Delete** - Remove tasks with confirmation dialog

### Additional Features
- ✅ User-specific task isolation (users only see their own tasks)
- ✅ Quick toggle button to mark tasks as done/pending
- ✅ Visual feedback for completed tasks (strikethrough, green background)
- ✅ Task timestamps (creation date)
- ✅ Success/error message notifications
- ✅ Responsive and clean UI design
- ✅ Django Admin panel integration

## 📸 Screenshots

### Login Page
![Login](images/login-page.png)
*Secure user authentication*

### Create New Task
![Create Task](images/create-task.png)
*Simple form to add new tasks*

### Task List View
![Task List](images/task-list.png)
*View all your tasks with quick action buttons*


### Task List Update
![Task Update](images/task-update.png)
*update your tasks*


### Delete Confirmation
![Delete](images/delete-confirm.png)


### Task List View
- Display all tasks with status indicators
- Quick action buttons (Done/Undo, Edit, Delete)
- Visual distinction between completed and pending tasks

### Create/Edit Task Form
- Simple form with title and description fields
- Checkbox to mark task as completed (edit mode)
- Form validation

### Authentication Pages
- Clean registration form with password validation
- Login page with error handling
- Automatic redirects after authentication

## 🛠️ Technologies Used

- **Backend Framework:** Django 5.0+
- **Database:** SQLite (default, can be changed to PostgreSQL/MySQL)
- **Frontend:** HTML5, CSS3
- **Authentication:** Django's built-in authentication system
- **Template Engine:** Django Template Language (DTL)

## 📦 Installation

### Prerequisites

- Python 3.8 or higher
- pip (Python package installer)
- Virtual environment (recommended)

### Step-by-Step Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/django-task-manager.git
   cd django-task-manager
   ```

2. **Create a virtual environment**
   ```bash
   # Windows
   python -m venv venv
   venv\Scripts\activate

   # Mac/Linux
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install django
   ```

4. **Navigate to project directory**
   ```bash
   cd taskmanager
   ```

5. **Run migrations**
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

6. **Create a superuser (admin account)**
   ```bash
   python manage.py createsuperuser
   ```
   Follow the prompts to set username and password.

7. **Run the development server**
   ```bash
   python manage.py runserver
   ```

8. **Access the application**
   - Main App: http://127.0.0.1:8000/
   - Admin Panel: http://127.0.0.1:8000/admin/

## 🚀 Usage

### For Regular Users

1. **Register an Account**
   - Navigate to the registration page
   - Create a username and password
   - Password must be at least 8 characters

2. **Login**
   - Use your credentials to log in
   - You'll be redirected to your task list

3. **Create Tasks**
   - Click "Create New Task" button
   - Fill in the title (required) and description (optional)
   - Submit the form

4. **Manage Tasks**
   - **Mark as Done:** Click the "✓ Done" button
   - **Undo Completion:** Click the "↩️ Undo" button
   - **Edit:** Click "Edit" to modify task details
   - **Delete:** Click "Delete" and confirm

5. **Logout**
   - Click "Logout" in the navigation menu

### For Administrators

1. **Access Admin Panel**
   - Go to http://127.0.0.1:8000/admin/
   - Login with superuser credentials

2. **Manage Users and Tasks**
   - View all users and their tasks
   - Manually create, edit, or delete tasks
   - Manage user accounts

## 📁 Project Structure

```
django-task-manager/
│
├── taskmanager/                 # Main project directory
│   ├── __init__.py
│   ├── settings.py             # Project settings
│   ├── urls.py                 # Project URL configuration
│   ├── wsgi.py
│   └── asgi.py
│
├── tasks/                       # Tasks app directory
│   ├── migrations/             # Database migrations
│   ├── templates/
│   │   └── tasks/              # HTML templates
│   │       ├── base.html       # Base template with navigation
│   │       ├── login.html      # Login page
│   │       ├── register.html   # Registration page
│   │       ├── task_list.html  # Task list view
│   │       ├── task_form.html  # Create/Edit form
│   │       └── task_confirm_delete.html
│   ├── __init__.py
│   ├── admin.py                # Admin panel configuration
│   ├── apps.py
│   ├── models.py               # Task model definition
│   ├── views.py                # View functions (CRUD + Auth)
│   ├── urls.py                 # App URL patterns
│   └── tests.py
│
├── manage.py                    # Django management script
├── db.sqlite3                   # SQLite database (created after migration)
└── README.md                    # This file
```

## 🔑 Key Files Explained

- **models.py** - Defines the Task model with fields (user, title, description, completed, created_at)
- **views.py** - Contains all view functions for authentication and CRUD operations
- **urls.py** - URL routing for the application
- **templates/** - HTML files for rendering pages
- **admin.py** - Configuration for Django admin interface

## 🎨 Features Breakdown

### Task Model Fields

| Field | Type | Description |
|-------|------|-------------|
| user | ForeignKey | Links task to user (for isolation) |
| title | CharField | Task title (max 200 chars) |
| description | TextField | Optional task details |
| completed | BooleanField | Task completion status |
| created_at | DateTimeField | Auto-generated timestamp |

### Views

| View | Purpose | Login Required |
|------|---------|----------------|
| register_view | User registration | No |
| login_view | User authentication | No |
| logout_view | User logout | No |
| task_list | Display all user tasks | Yes |
| task_create | Create new task | Yes |
| task_update | Edit existing task | Yes |
| task_delete | Delete task | Yes |
| task_toggle_complete | Quick mark as done/pending | Yes |



Author - Sunil
