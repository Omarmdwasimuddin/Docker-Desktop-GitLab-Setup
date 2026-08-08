# Docker Desktop দিয়ে GitLab Setup

এই ডকুমেন্টে দেখানো হয়েছে কিভাবে Docker Desktop ব্যবহার করে লোকাল মেশিনে GitLab (GitLab CE) সেটআপ করা যায়।

---

## ধাপ ১: GitLab এর Docker Image খুঁজে বের করা

Browser এ গিয়ে সার্চ করো: `gitlab docker hub`

অথবা ক্লিক কর URL Link:

👉 https://hub.docker.com/r/gitlab/gitlab-ce

![Docker Hub search](https://imgur.com/4TIw6BX.png)

---

## ধাপ ২: Pull Command Copy করা

Docker Hub এর page থেকে image pull করার command টা copy করো।

![Pull command](https://imgur.com/VxipliP.png)

---

## ধাপ ৩: Image Pull করা

Docker Desktop এর terminal open করে copy করা command টা paste করো:

```bash
docker pull gitlab/gitlab-ce
```

![Docker pull](https://imgur.com/AO3v7FS.png)

---

## ধাপ ৪: GitLab Container Run করা

এখন নিচের command দিয়ে GitLab এর container run করো:

```bash
docker run -p 8000:80 gitlab/gitlab-ce
```

> **Note:** এই command এর মাধ্যমে container এর port `80` কে host machine এর port `8000` এর সাথে map করা হচ্ছে। এই terminal টা চলতে থাকবে, বন্ধ করা যাবে না।

---

## ধাপ ৫: Browser এ GitLab Open করা

Browser এ গিয়ে নিচের URL এ যাও:

```
http://localhost:8000/users/sign_in
```

GitLab পুরোপুরি চালু হতে কিছুক্ষণ সময় লাগবে (initialization চলবে), তাই একটু wait করতে হবে।

![Loading page](https://imgur.com/izVpjzA.png)

---

## ধাপ ৬: Login Credentials বের করা

Sign in করার জন্য আমাদের লাগবে **Username or primary email** এবং **Password**।

![Sign in page](https://imgur.com/o1ieTTL.png)

### Container ID বের করা

Docker Desktop এ **নতুন একটা terminal open করো** (আগের terminal টা বন্ধ করা যাবে না, কারণ ওটাতেই GitLab চলছে) এবং নিচের command দাও:

![New terminal](https://imgur.com/3itBEdj.png)

```bash
docker ps -l
```

এই command থেকে running container এর **Container ID** copy করে নাও।

![Container ID](https://imgur.com/V7QJUK0.png)

### Initial Root Password বের করা

Container ID কে নিচের command এ বসিয়ে run করো (যেমন এখানে `682e19f3358c` হলো একটা উদাহরণ, তোমার নিজের container ID বসাতে হবে):

```bash
docker exec -it 682e19f3358c cat /etc/gitlab/initial_root_password
```

---

## ধাপ ৭: Login করা

উপরের command থেকে যে password পাওয়া গেছে, সেটা copy করো।

![Password](https://imgur.com/3A6UMul.png)

এরপর Sign in page এ গিয়ে:
- **Username or primary email:** `root`
- **Password:** copy করা password টা paste করো

![Login](https://imgur.com/ug3rgFZ.png)

---

## ধাপ ৮: Initial Setup (Optional)

Login করার পর কিছু setup option দেখাবে — চাইলে সেগুলো এখনই setup করা যাবে, অথবা skip করে পরে করা যাবে।

![Setup options](https://imgur.com/qgOQ0EK.png)
![Setup options](https://imgur.com/VjETMoG.png)

---

## ধাপ ৯: Dashboard

সব setup শেষ হলে GitLab এর dashboard দেখা যাবে — এখান থেকেই project তৈরি, repository manage, CI/CD pipeline সবকিছু করা যাবে।

![Dashboard](https://imgur.com/UK6nPqr.png)

---

## সংক্ষেপে Command গুলো

```bash
# Image pull করা
docker pull gitlab/gitlab-ce

# Container run করা
docker run -p 8000:80 gitlab/gitlab-ce

# Running container দেখা (নতুন terminal এ)
docker ps -l

# Root password বের করা
docker exec -it <container_id> cat /etc/gitlab/initial_root_password
```
