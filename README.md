# Docker Compose Project

This project utilizes Docker Compose to orchestrate multiple services, including two web servers and a reverse proxy. Each service is based on the lightweight `nginx:alpine` image.

## Services

### Web1 and Web2

- **Purpose**: Serve static content.
- **Image**: `nginx:alpine`
- **Volumes**: Maps `./web1` and `./web2` from the host to `/usr/share/nginx/html` in the containers, respectively. This setup allows serving static content from these directories.
- **Networks**: Both services are attached to a custom network named `backend`, facilitating internal communication while isolating them from unauthorized external access.

### Reverse Proxy

- **Purpose**: Route incoming traffic to `web1` and `web2` services.
- **Image**: `nginx:alpine`
- **Ports**: Exposes ports `80` and `443` to handle HTTP and HTTPS traffic, respectively.

## Getting Started

To run this project, you need Docker and Docker Compose installed on your machine.

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd <repository-name># Docker Compose Project

This project utilizes Docker Compose to orchestrate multiple services, including two web servers and a reverse proxy. Each service is based on the lightweight `nginx:alpine` image.

## Services

### Web1 and Web2

- **Purpose**: Serve static content.
- **Image**: `nginx:alpine`
- **Volumes**: Maps `./web1` and `./web2` from the host to `/usr/share/nginx/html` in the containers, respectively. This setup allows serving static content from these directories.
- **Networks**: Both services are attached to a custom network named `backend`, facilitating internal communication while isolating them from unauthorized external access.

### Reverse Proxy

- **Purpose**: Route incoming traffic to `web1` and `web2` services.
- **Image**: `nginx:alpine`
- **Ports**: Exposes ports `80` and `443` to handle HTTP and HTTPS traffic, respectively.

## Getting Started

To run this project, you need Docker and Docker Compose installed on your machine.

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd <repository-name>
2. **Start the services**:
    ```
    docker-compose up -d
    ```

This command starts the services in detached mode.

Access the services:

- Access the web services directly using their respective ports (configured in the Docker Compose file).
- Access the web services via the reverse proxy through the exposed ports `80` and `443`.

**Customization**
- Static Content: To serve your static content, replace the contents of the `./web1` and `./web2` directories with your own HTML, CSS, and JavaScript files.
- Configuration: Modify the Nginx configuration as needed to adjust to your requirements, including the reverse proxy settings.

**Stopping the Services**

To stop and remove all the running services, use the following command:

```
docker-compose down
```
