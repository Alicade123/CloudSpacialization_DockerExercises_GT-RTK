### What you will learn

- Application Dockerfiles
- Node.js runtime images
- Dependencies
- `WORKDIR`
- Application startup
- Ports

### Tasks

Use the **Express application provided in the ZIP file above for the challenges.**

Containerize the application so it runs entirely inside Docker.

### Requirements

1. Extract the Express project.
2. Create a Dockerfile.
3. Use an appropriate Node.js base image.
4. Set an application working directory.
5. Install application dependencies inside the image.
6. Copy the application source code.
7. Configure the application to listen on the container network
    
    interface.
    
8. Expose the application's HTTP port.
9. Configure the container startup command.
10. Build the image.
11. Run the application as a container.
12. Verify an application endpoint from the host.

- **`*D:\Specialization Trainigs\docker-exercises> docker build --no-cache  -t express:v1.0 .\docker-exercises\express\*`**
- **`*docker images*`**
- **`*docker run -d --name express_app -p 5000:5000 express:v1.0*`**
- **`*http://localhost:5000/*`**
- **`*docker ps*`**
- **`*docker logs —since 15m -t express_app*`**

```jsx
FROM node:24-slim

WORKDIR /app

COPY package*.json ./

RUN npm install 

COPY server.js ./

EXPOSE 5000

CMD ["node", "server.js"]
```