# Basic from dockerfiles

Dockerfiles are files to create docker images with certain specifications. Dockerfile example:

```dockerfile
FROM nginx:1.11-alpine
COPY index.html /usr/share/nginx/html
EXPOSE 80
```

creates a image from nginx and copies index.html from local directory to nginx/html and exposes port 80
