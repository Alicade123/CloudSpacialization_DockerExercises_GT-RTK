FROM python:3.6-slim

WORKDIR /app

COPY requirements.txt ./

RUN pip install --no-cache-dir -r requirements.txt

RUN pip install --no-cache-dir --upgrade gunicorn

COPY . .

EXPOSE 8000

# Collect static files for production (standard Django requirement) -CSS stylesheets, frontend JavaScript files, images, and logos
RUN python manage.py collectstatic --noinput

# Run Gunicorn :: Syntax: "project_config_folder_name.wsgi:application"
CMD ["gunicorn", "--workers", "3", "--bind", "0.0.0.0:8000", "hello.wsgi:application"]
