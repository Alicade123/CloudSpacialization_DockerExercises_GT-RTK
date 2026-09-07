FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

RUN pip install --no-cache-dir --upgrade gunicorn flask

COPY . .

EXPOSE 5000

# Run Gunicorn :: Syntax: "project_config_folder_name.wsgi:application"
CMD ["gunicorn", "--workers", "3", "--bind", "0.0.0.0:5000", "hello.app:create_app()"]

