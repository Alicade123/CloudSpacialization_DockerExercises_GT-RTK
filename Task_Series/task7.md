# Project 07 — **Containerize a Python Application**

### What you will learn

- Python runtime images
- Dependency files
- Application startup
- Runtime configuration

### Tasks

Choose **one Python application provided in the ZIP file above for the challenges.**

- Django
- Flask

Containerize it.

### Requirements

1. Create a Dockerfile.
2. Use an appropriate Python base image.
3. Install the application's dependencies inside the image.
4. Copy the application source code.
5. Configure the application to listen on the container network
    
    interface.
    
6. Expose the application's port.
7. Configure the startup command.
8. Build and run the image.
9. Verify the application from the host.

### *Django*

```jsx
*FROM python:3.6-slim

WORKDIR /app

COPY requirements.txt ./

RUN pip install --no-cache-dir -r requirements.txt

RUN pip install --no-cache-dir --upgrade gunicorn

COPY . .

EXPOSE 8000

# Collect static files for production (standard Django requirement) -CSS stylesheets, frontend JavaScript files, images, and logos
RUN python manage.py collectstatic --noinput

# Run Gunicorn :: Syntax: "project_config_folder_name.wsgi:application"
CMD ["gunicorn", "--workers", "3", "--bind", "0.0.0.0:8000", "hello.wsgi:application"]*

```

- `*docker build -t django_app:latest .\docker-exercises\django\*`
- `*docker run -d --name django_app -p 8000:8000 django_app:latest*`
- `*docker ps*`
- `*http://localhost:8000/*`
- `*docker stop django_app*`

### *Flash*

```docker
*FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

RUN pip install --no-cache-dir --upgrade gunicorn flask

COPY . .

EXPOSE 5000

# Run Gunicorn :: Syntax: "project_config_folder_name.wsgi:application"
CMD ["gunicorn", "--workers", "3", "--bind", "0.0.0.0:5000", "hello.app:create_app()"]*

```

- `*docker build -t flash_app:v1.0 .\docker-exercises\flash\*`
- `*docker run -d --name flash_app -p 5000:5000 flash:v1.0*`
- `*docker ps*`
- http://localhost:5000
- `*docker stop flash_app*`