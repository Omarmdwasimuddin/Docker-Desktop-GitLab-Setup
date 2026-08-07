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
#### kichukhon wait korte hobe
![](https://imgur.com/izVpjzA.png)

---

#### ekhon amader lagbe Username or primary email and Password 
![](https://imgur.com/o1ieTTL.png)
#### docker e new terminal open koro and command daw (ager terminal stop korar jabe na)
![](https://imgur.com/3itBEdj.png)
```bash
docker ps -l
```

#### container id copy koro
![](https://imgur.com/V7QJUK0.png)
#### terminal e command koro [ei command e container id o paste kora hoyeche]
```bash
docker exec -it 682e19f3358c cat /etc/gitlab/initial_root_password
```
---
#### password copy koro
![](https://imgur.com/3A6UMul.png)
#### Username or primary email: root  daw ar Password: paste koro.
![](https://imgur.com/ug3rgFZ.png)

#### kichu jinish setup chaite pari skip korte parbe ba set up korte parbe.
![](https://imgur.com/C6sucA8.png)

#### dashboard
![](https://imgur.com/UK6nPqr.png)
