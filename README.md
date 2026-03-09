
## 🖥️ Environment Setup

### Part 1 – Installing Docker

Docker Desktop was downloaded from [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/) and installed on the local machine.

**Verification:**

```bash
docker version
```

**Output:**
```
Client:
 Version:           29.2.1
 API version:       1.53
 Go version:        go1.25.6
 Git commit:        a5c7197
 Built:             Mon Feb  2 17:20:16 2026
 OS/Arch:           windows/amd64
 Context:           desktop-linux

Server: Docker Desktop 4.63.0 (220185)
 Engine:
  Version:          29.2.1
  API version:      1.53 (minimum version 1.44)
  Go version:       go1.25.6
  Git commit:       6bc6209
  Built:            Mon Feb  2 17:17:24 2026
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          v2.2.1
  GitCommit:        dea7da592f5d1d2b7755e3a161be07f43fad8f75
 runc:
  Version:          1.3.4
  GitCommit:        v1.3.4-0-gd6d73eb8
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0
```

> 📷 **Screenshot – Docker Version Verification:**
> [Docker version output](./screenshots/docker_version.png)

---

### Part 2 – Deploying DVWA

**Pull the DVWA Docker image:**

```bash
docker pull vulnerables/web-dvwa
```

**Run the container:**

```bash
docker run -d \
  --name dvwa \
  -p 8080:80 \
  vulnerables/web-dvwa
```

**Verify it is running:**

```bash
docker ps
```

**Expected output:**

```
CONTAINER ID   IMAGE                  COMMAND      CREATED          STATUS          PORTS                                     NAMES
55fe2aa95aa6   vulnerables/web-dvwa   "/main.sh"   42 seconds ago   Up 41 seconds   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   dvwa
```

**Accessing DVWA:**

- URL: `http://localhost:8080`
- Clicked **"Create / Reset Database"**
- Logged in with:
  - **Username:** `admin`
  - **Password:** `password`

> 📷 [Screenshot: DVWA login page and dashboard after successful login](./screenshots/DVWA_login.png)

---
