## Project 05 — **Build a Custom Nginx Image**

### What you will learn

- Dockerfiles
- Base images
- `COPY`
- Build context
- Custom images

### Tasks

Create an HTML page containing:

```
Hello from my Docker image!
```

Build a custom Nginx image that serves this page.

### Requirements

1. Create a Dockerfile.
2. Use `nginx:alpine` as the base image.
3. Copy the HTML page into the correct Nginx web directory.
4. Build an image with your own name.
5. Run a container from your image.
6. Publish the HTTP port.
7. Verify the custom page from the host.