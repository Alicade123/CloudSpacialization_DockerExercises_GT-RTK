# Project 02 — **Inspect and Enter an Apache Container**

### What you will learn

- Container inspection
- Executing commands inside containers
- Container filesystems
- Running processes

### Tasks

Run an Apache HTTP server using: `httpd:2.4`

Enter the container and inspect how Apache is configured.

### Requirements

1. Run an `httpd:2.4` container.
2. Enter the running container.
3. Locate Apache's web document directory.
4. Inspect the default HTML file.
5. Identify the process running Apache.
6. Exit the container.
7. Stop and remove the container.

### Verification

- [ ]  You can locate the web document directory.
- [ ]  You can identify the Apache process.
- [ ]  You can explain how you entered the container.

### Resolutions

- `*docker run -d --name my-apache-container httpd:2.4*`
- `*docker exec -it my-apache-container bash*`
- `*cd /usr/local/apache2/htdocs/*`
- `*ls*`
- `cat index.html*`
- `*ps aux*`
- `*apt-get update && apt-get install -y procps*`
- `*ls -l /proc*`
- `*exit*`
- `*docker stop my-apache-container*`
- `*docker rm my-apache-container*`
