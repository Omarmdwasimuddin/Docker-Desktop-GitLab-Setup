## Docker-Desktop: GitLab Setup

#### browser e search koro: gitlab docker hub (image e show hoya url click koro) ---> ba click koro: https://hub.docker.com/r/gitlab/gitlab-ce
![](https://imgur.com/4TIw6BX.png)

#### command copy koro
![](https://imgur.com/VxipliP.png)

#### Docker Desktop er ternimal e command paste koro
```bash
docker pull gitlab/gitlab-ce
```
![](https://imgur.com/AO3v7FS.png)
#### docker e gitlab run koro
```bash
docker run -p 8000:80 gitlab/gitlab-ce
```
---

#### browser e daw
```bash
http://localhost:8000/users/sign_in
```
---
