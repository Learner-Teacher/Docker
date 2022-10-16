# Docker Interview Savollari
# 🛑🛑ISHLAB CHIQISH JARAYONIDA🛑🛑
Biz docker bo'yicha intervyu savollarini jamlashga qaror qildik va sizga foydasi tegadi degan umiddamiz.

## Mundarija

<br/>

| No: |               Savollar          |
|-----|---------------------------------|
| 1.  |[Docker nima?](#docker-nima-)|
| 2.  |[Docker continer nima?](#Docker-container-nima-)|
| 3.  |[Docker image nima?](#docker-image-nima-)|
| 4.  |[Docker HUB nima?](#docker-hub-nima-)|
| 5.  |[Docker arxitekturasini tushuntirib bering?](#docker-arxitekturasini-tushuntirib-bering-)|
| 6.  |[Dockerfile nima?](#dockerfile-nima-)|
| 7.  |[Docker Compose haqida gapirib bering?](#docker-compose-haqida-gapirib-bering-)|
| 8.  |[Dockerfile Docker compose dan qanaqa farqi bor?](#dockerfile-docker-compose-dan-qanaqa-farqi-bor-)|
| 9.  |[Docker Swarm nima?](#docker-swarm-nima-)|
| 10. |[Docker Namespace nima?](#docker-namespace-nima-)|
| 11. |[What is the lifecycle of a Docker Container?](#what-is-the-lifecycle-of-a-docker-container-)|
| 12. |[Docker Machine ni tushuntirib bering?](#docker-machine-ni-tushuntirib-bering-)|
| 13. |[Ishlayotgan container nin ichiga qanday kirasiz ?](#ishlayotgan-container-nin-ichiga-qanday-kirasiz-)|
| 14. |[Docker container dan chiqib ketsangiz ma'lumot o'chib ketadimi ?](#docker-container-dan-chiqib-ketsangiz-malumot-ochib-ketadimi-)|
| 15. |[Docker qayerda ishlatiladi ?](#docker-qayerda-ishlatiladi-)|
| 16. |[Docker boshqa konteynerlashtirish usullaridan nimasi bilan farq qiladi?](#docker-boshqa-konteynerlashtirish-usullaridan-nimasi-bilan-farq-qiladi-)|

<br/>


##  ***🔖Docker nima ?***

**Docker** - bu konteynerlashtirish platformasi bo'lib, ilovangiz va uning barcha bog'liqliklarini konteynerlar ko'rinishida birlashtirib, ilovangiz har qanday muhitda, xoh u ishlab chiqish, sinovdan o'tkazish yoki ishlab chiqarishda muammosiz ishlashini ta'minlaydi.

<p align="center">
  <img src="image/docker-architecture.png" alt="Docker Architecture" width="600px" />
</p>


<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Docker container nima ?***

**Docker container** - bu docker image larni ishga tushirilgan variantidir. Tashqi muhitdan izolatsiyalanga holda ishlaydi. Izolyatsiyalangan deganda tizimda boshqa jarayonlar bilan bog’lanmagan  holda ishlaydi.

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Docker image nima ?***

**Docker image** - bu Docker containerining manbai hisoblanadi. Docker image containerlarni yaratish uchun ishlatiladi. Agar foydalanuvchi Docker imageni ishga tushirsa, containerning namunasi yaratiladi. Ushbu docker image lari har qanday Docker muhitiga joylashtirilishi mumkin. 

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Docker HUB nima ?***

**Docker Hub** - bu siz yaratgan docker imagelar saqlash mumkin bo’lgan joy ya’ni image lar saqlanadigan ombor hisoblnadi. U joyda hamma uchun umumiy bo’lgan docker imagelar oldindan yozib qo’yilgan siz ulardan olib foydalanishingiz ham mumkin va boshqalarga foydasi tegishi uchun o’zingiz yozgan docker imageni ham ular uchun taqdim etsangiz bo’ladi :)

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Docker arxitekturasini tushuntirib bering ?***

**Docker mijoz-server arxitekturasi**da ishlaydi. Docker mijozi Docker Daemon bilan aloqa o'rnatadi. Docker mijozi va Daemon bir xil tizimda ishlashi mumkin. Docker mijozi masofaviy Docker Daemoniga ham ulanishi mumkin. Docker arxitekturasidagi Docker komponentlarining har xil turlari bor va ular quyidagilardir:

- **Docker Client**: Bu Docker Host bilan aloqa o'rnatish uchun Docker qurish va ishga tushirish operatsiyalarini bajaradi. Docker buyrug'i bajariladigan so'rovlarni chaqirish uchun Docker API-dan foydalanadi.
  
- **Docker Xost**: Ushbu komponentda Docker Demoni, Konteynerlar va uning tasvirlari mavjud. Tasvirlar konteynerlarda saqlanadigan ilovalar uchun metadata turi bo'ladi. Docker Demoni Registry bilan aloqa o'rnatadi.
  
- **Registry**: Ushbu komponent Docker tasvirlarini saqlaydi. Umumiy registrlar Docker Hub va Docker Cloud bo'lib, ulardan har kim foydalanishi mumkin.

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Dockerfile nima ?***

Docker **Dockerfile** deb nomlangan fayldagi ko'rsatmalarni o'qish orqali avtomatik ravishda tasvirlarni yaratishi mumkin. Dockerfile - bu foydalanuvchi image ni yig'ish uchun buyruq satrida chaqirishi mumkin bo'lgan barcha buyruqlarni o'z ichiga olgan matnli hujjat. Docker build-dan foydalanib, foydalanuvchilar bir nechta buyruq qatori ko'rsatmalarini ketma-ket bajaradigan avtomatlashtirilgan tuzilmani yaratishi mumkin.

### Misol uchun:

```js
# alpine will download only basic version of node.js
FROM node:alpine

# Instead of root directory, program will use "/usr/app" directory
WORKDIR /usr/app

# Copy local directory to nodejs directory
COPY ./ ./

# Perform npm install
RUN npm install

# Run npm start in command prompt
CMD ["npm", "start"]
```
```js
docker build -t sofyspace/scm-website:latest .        // --tag , -t   ==> Name and optionally a tag in the 'name:tag' format
docker run -p 3000:3000 sofyspace/scm-website         // Project will run on local and will map to docker conatiner port 
```
<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Docker Compose haqida gapirib bering ?***

**Docker Compose** - bu ko'p konteynerli Docker ilovalarini aniqlash va ishga tushirish vositasi. Compose yordamida siz ilova xizmatlarini sozlash uchun YAML faylidan foydalanasiz. Keyin, bitta buyruq bilan siz konfiguratsiyangizdan barcha xizmatlarni yaratasiz va ishga tushirasiz. Docker Compose-dan alohida konteynerlar yaratish, ularni joylashtirish va bir-biri bilan mu'loqot qilish uchun foydalanishingiz mumkin. Har bir konteyner boshqa konteynerlar bilan aloqa qilish uchun portni ochadi.

**Misol uchun:**  MySQL service ni ko'rsak
```js
version: "3.7"

services:
  app:
    image: node:12-alpine
    command: sh -c "yarn install && yarn run dev"
    ports:
      - 3000:3000
    working_dir: /app
    volumes:
      - ./:/app
    environment:
      MYSQL_HOST: mysql
      MYSQL_USER: root
      MYSQL_PASSWORD: secret
      MYSQL_DB: todos

  mysql:
    image: mysql:5.7
    volumes:
      - todo-mysql-data:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: secret
      MYSQL_DATABASE: todos

volumes:
  todo-mysql-data:
```
```js
docker-compose up  // Start the App
docker-compose down   // Removing Volumes
```
<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Dockerfile Docker compose dan qanaqa farqi bor ?***

**Dockerfile** - bu oddiy matnli fayl bo'lib, unda foydalanuvchi tasvirni yig'ish uchun chaqirishi mumkin bo'lgan buyruqlar mavjud, 

**Docker Compose** esa ko'p konteynerli Docker ilovalarini aniqlash va ishga tushirish uchun vositadir. Docker Compose ilovangizni tashkil etuvchi xizmatlarni docker-compose.yml da aniqlaydi, shunda ular alohida muhitda birgalikda ishlaydi. U faqat docker-compose-ni ishga tushirish orqali bitta buyruqda ishlaydigan ilovani oladi. Agar loyihangizning docker-compose.yml fayliga qurish buyrug'i qo'shilsa, 
Docker compose Dockerfile faylidan foydalanadi. Sizning Docker ish jarayoni siz yaratmoqchi bo'lgan har bir image uchun mos Dockerfile yaratish bo'lishi kerak, so'ngra qurish buyrug'i yordamida image larni yig'ish uchun kompozitsiyadan foydalaning.

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Docker Swarm nima ?***

**Docker Swarm** - bu Docker uchun mahalliy klaster. U Docker xostlar partalini yagona virtual Docker xostiga aylantiradi. Docker Swarm standart Docker API-ga xizmat qiladi, Docker daemoni bilan allaqachon aloqada bo'lgan har qanday vosita Swarm-dan bir nechta xostlarni shaffof ravishda o'lchash uchun foydalanishi mumkin.

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Docker Namespace nima ?***

**Docker Namespace**  Linux xususiyatlaridan biri va konteynerlarning muhim tushunchasidir. Namespace konteynerlarda izolyatsiya qatlamini qo'shadi. Docker portativ bo'lib qolish va asosiy xost tizimiga ta'sir qilmaslik uchun turli nomlar bo'shliqlarini taqdim etadi. Docker tomonidan qo'llab-quvvatlanadigan bir nechta nom maydoni turlari - PID, Mount, IPC, User, Network

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖What is the lifecycle of a Docker Container ?***

Docker konteynerlari quyidagi hayot aylanishiga ega:

  1. Konteyner yaratish

  2. Konteynerni ishga tushirish

  3. Konteynerni to'xtatib turish (ixtiyoriy)
  
  4. To'xtab turgan Konteynerni ishga tushirish (ixtiyoriy)
  
  5. Konteynerni ishga tushirish
  
  6. Konteynerni to'xtatish
  
  7. Konteynerni qayta ishga tushirish
  
  8. Konteynerni o'chirish
  
  9. Konteynerni yo'q qilish

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Docker Machine ni tushuntirib bering ?***

**Docker Machine** - virtual xostlarga Docker Engine o'rnatish imkonini beruvchi vositadir. Endi bu xostlarni docker-machine buyruqlari yordamida boshqarish mumkin. Docker Machine sizga Docker Swarm klasterlarini ta'minlashga ham imkon beradi.

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Ishlayotgan container ning ichiga qanday kirasiz ?***

Quyidagi buyruq bizga ishlaydigan konteynerga kirish imkonini beradi:
```js
docker exec -it bash
```
**Exec** buyrug'i konteyner ichiga kirish va u bilan ishlash imkonini beradi.

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Docker container dan chiqib ketsangiz ma'lumot o'chib ketadimi ?***

**Yo'q**, Docker konteyneri chiqqanda siz hech qanday ma'lumotni yo'qotmaysiz. Ilovangiz konteynerga yozgan har qanday ma'lumotlar siz konteynerni aniq o'chirmaguningizcha diskda saqlanadi. Konteynerning fayl tizimi konteyner to'xtagandan keyin ham saqlanib qoladi.

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Docker qayerda ishlatiladi ?***

Docker quyidagi sohalarda qo'llaniladi:

* **Simplifying configuration :**  Docker sizga muhit va konfiguratsiyani kodga kiritish va uni joylashtirish imkonini beradi.

* **Code Pipeline boshqarish :** Ishlab chiqish va ishlab chiqarish uchun turli xil tizimlar qo'llaniladi. Kod ishlab chiqishdan sinovdan ishlab chiqarishgacha o'tganda, u atrof-muhitdagi farqdan o'tadi. Docker Code Pipeline lari mustahkamligini saqlashga yordam beradi.

* **Developer Productivity :** ishlab chiqish uchun Docker-dan foydalanish bizga ikkita narsani beradi - biz ishlab chiqarishga yaqinroqmiz va rivojlanish muhiti tezroq quriladi.

* **Application Isolation :** Konteynerlar barcha bog'liqliklar bilan birga o'ralgan ilovalar bo'lgani uchun ilovalaringiz izolyatsiya qilingan. Ular Docker-ni qo'llab-quvvatlaydigan har qanday uskunada mustaqil ishlashlari mumkin.

* **Debugging Capabilities :** Docker konteynerlarga xos bo'lmagan, ammo konteynerlar bilan yaxshi ishlaydigan turli tuzatish vositalarini qo'llab-quvvatlaydi.

* **Multi-tenancy :** Docker sizga kodlaringiz va joylashtirishlaringizdagi ortiqcha narsalarni oldini oluvchi ko'p foydalanuvchi ilovalariga ega bo'lish imkonini beradi.

* **Rapid Deployment :** Docker butun operatsion tizimni noldan qurish zaruratini yo'q qiladi va joylashtirish vaqtini qisqartiradi.

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>

##  ***🔖Docker boshqa konteynerlashtirish usullaridan nimasi bilan farq qiladi ?***

**Docker konteyner**larini har qanday bulutli platformada joylashtirish juda oson. Boshqa texnologiyalar bilan solishtirganda, u bir xil uskunada ishlaydigan ko'proq ilovalarni olishi mumkin, bu ishlab chiquvchilarga tezda, ishga tushirishga tayyor konteynerli ilovalarni yaratishni osonlashtiradi va ilovalarni boshqarish va joylashtirishni ancha osonlashtiradi. Siz hatto ilovalaringiz bilan konteynerlarni baham ko'rishingiz mumkin.

<div align="right">
     <b><a href="#mundarija">↥ back to top</a></b>
</div>




↘️➡️⬇️⬇️⬇️**Davom etayabdi** ⬇️⬇️⬇️⬅️↙️