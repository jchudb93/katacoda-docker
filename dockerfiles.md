# Basic from dockerfiles

Dockerfiles are files to create docker images with certain specifications. Dockerfile example:

```dockerfile
FROM nginx:1.11-alpine
COPY index.html /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

Creates a image from nginx and copies index.html from local directory to nginx/html and exposes port 80. Then runs the command "nginx -g daemon off". Finally build the image with " docker build -t my-nginx-image:latest . "
