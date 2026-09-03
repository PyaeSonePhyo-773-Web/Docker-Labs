# 01 - Docker Basic Commands 🐳

My first hands-on Docker lab, covering the fundamentals of Docker images, containers, port mapping, container lifecycle, and basic container interaction.

## 🎯 What I Learned

- Docker images vs containers
- Interactive and detached containers
- Port mapping
- Container lifecycle management
- Container logs and shell access
- Temporary containers and cleanup

## Stracture

             Docker Image
                  │
                  ↓
             docker run
                  │
                  ↓
              Container
                  │
        ┌─────────┴─────────┐
        ↓                   ↓
    docker ps          docker logs
        │
        ↓
   docker exec
        │
        ↓
   Access Container
        │
        ↓
 stop / start / restart
        │
        ↓
     docker rm

## 🛠️ Commands Practiced

### Docker Basics

```bash
docker --version
docker info
docker pull hello-world
docker run hello-world
````

### Containers

```bash
docker run -it ubuntu bash
docker ps
docker ps -a
docker logs nginx
```

### Nginx & Port Mapping

```bash
docker run -d --name nginx -p 8080:80 nginx
```

Port mapping:

```text
localhost:8080 → nginx:80
```

Verify with:

```powershell
curl.exe http://localhost:8080
```

Result:

```text
<h1>Welcome to nginx!</h1>
```

## 🔄 Container Lifecycle

```bash
docker stop nginx
docker start nginx
docker restart nginx
docker rm nginx
```

Access a running container:

```bash
docker exec -it nginx /bin/bash
```

Inside the container:

```bash
cat /etc/os-release
ls /usr/share/nginx/html
```

## 🧹 Cleanup

```bash
docker container prune
docker system prune
```

## 📸 Lab Evidence

### Nginx Container Running

![Nginx Container](./screenshots/nginx-running.png)

### Nginx HTTP Response

![Nginx curl Test](./screenshots/nginx-curl.png)

## 📚 Key Takeaway

```text
Image
  ↓
docker run
  ↓
Container
  ↓
docker ps / logs / exec
  ↓
stop / start / restart
  ↓
remove
```

Successfully deployed and verified an **Nginx container using Docker**.

Author - Pyae Sone Phyo


