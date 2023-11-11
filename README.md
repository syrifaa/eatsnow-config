# EatsNow Config
> Web Service SOAP and REST. Click [here to spek](https://docs.google.com/document/d/1EY768mL9MYEdoUNIfIcRTLOmiyOvlCUKaH9cV9RBDy0/edit)

## SPEK
<!-- dropdown -->
<details>
<summary><b>TOOLS</b></summary>

1. REST
    - __NodeJS__
    - __MySQL__ atau __PostgreSQL__
    - boleh pakai _ORM_
    - boleh pakai _library_

2. SOAP
    - __Java__
    - kakas __Jax-WS (Java Servlet)__
    - __MySQL__
    - boleh pakai _ORM_

3. SPA
    - __ReactJS__ atau __ReactTS__
    - komunikasi hanya dengan __REST API__ 
    - boleh pakai _library_
4. PHP App
    - boleh ubah _DB_
    - kasih perubahan di __README.md__

</details>

<details>
<summary><b>TEKNIS</b></summary>

1. REST
    - __Fitur tambahan = 4__
        - __1__ nya ada komunikasi dengan __SOAP__
        - contoh: _premium user_ = bisa liat apa gitu
    - __Autentikasi__ __JWT__ atau __OAuth2__ pada protokol _rest_
    - __RESTFUL__
    - saran library = __ExpressJS__ dan __Fastify__
2. SOAP
    - __Fitur tambahan = 3__
        - tidak termasuk _logging_
        - contoh: _subscription_
    - Service pakai __Jax-WS__
    - __MySQL__
    - __API Key__ untuk kunci memanggil _SOAP Server/Subscription Service_
        - _callback request_ ke _Plain Web Service_
        - generate key (rekomen manual) dan simpan di __berkas Environment__ tiap __service__
        - validasi API Key di __SOAP SERVICE__ (kayak password punya SOAP)
        - API Key di _Plain Web Service_ dan _REST_ harus __BEDA__ => _SOAP_ bisa __BEDAIN__ _service_ mana yang __manggil__ (logging)

3. ENTITY
    - __2__ entity (not include _user_) di __REST__
    - __1__ entity (not include _logging_) di __SOAP__
    - entity __logging__ di __SOAP__ = mencatat semua __Request__ yang masuk ke _service SOAP_
    - wajib kolom
        - __req desc__ = bisa _body_ dan _parameter_ request
        - __IP__
        - __endpoint destination__
        - __timestamp__
    - ada rekomen kolom
        - __API Key__ = untuk _SOAP_ = __API Key__ yang dipakai _Plain Web Service_ untuk manggil _SOAP_
        - __status__ = _success_ atau _failed_
        - __response__ = _body_ dan _parameter_ response

4. CLIENT SPA
    - minimal __4 page__ selain _autentikasi_ (login register)
    - __navbar__ di _tiap halaman_. Minimal 2 hyperlink
    - __validasi input__ dan __error handling__
        - ex: required field, format email, dll
    - _SPA_ HANYA bisa __request__ ke __REST__. __Data__ hanya bisa didapat dari __REST__

5. CONSTRAINT
    - __Routing, model, handler function__ di __REST__ wajib buat sendiri
    - _library/framework_ gaboleh yang bisa _generate/menghindari_ coding seperti _Content Management System_ (Library Strapi)
    - React boleh pake kakas styling
    - saran __development server__
        - Vite = pake rollup dan lebih cepet daripada CRA
        - setup lewat webpack sendiri
        - serving React lewat server framework seperti __Express__
    - rekomen __TypeScript__ 

</details>

<details>
<summary><b>BONUS</b></summary>

1. ALL RESPONSIVE DESIGN
    - 1280 x 768
    - 800 x 600
2. DOCKER
3. TEMBOLOK/CACHING
    - minimal __2 fungsi__ di __rest__
    - bisa di level __query__ atau __response__
    - pakai __Redis__
4. OWASP
5. MAILING

</details>

<details>
<summary><b>DELIVERABLES</b></summary>

1. GRUP DI GITLAB
    - IF3110-2023-02-XX
    - XX = huruf kelompok
2. Tambah 4 Repo
    - PHP App (PHP + HTML-CSS-JS)
    - REST Service (Rest, NodeJS)
    - SOAP Service (SOAP, JAX-WS)
    - Client SPA (ReactJS/ReactTS)
    - Config (Dockerfile, docker-compose.yml)
3. README.md
    - upgrade readme di __PHP APP__. isinya perubahan yang dilakukan
    - __REST__ dan __SOAP__ = dokumentasi API
        - __Deskripsi singkat__ web service
        - __Skema basis data__ yang digunakan
        - __Endpoint API__
        - (optional) __Payload__ dan __response API__
        - __Pembagian tugas__. [ini format](https://docs.google.com/document/d/1EY768mL9MYEdoUNIfIcRTLOmiyOvlCUKaH9cV9RBDy0/edit#heading=h.758toy7ewj9c)

    - __SPA__ = dokumentasi aplikasi
        - __Deskripsi singkat__ aplikasi
        - __SS__ tampilan. minimal __1 per page__
        - __Pembagian tugas__. [ini format](https://docs.google.com/document/d/1EY768mL9MYEdoUNIfIcRTLOmiyOvlCUKaH9cV9RBDy0/edit#heading=h.758toy7ewj9c)
4. SQL SEEDING
    - mengisi data awal buat __Demo__
    - boleh pakai data yang udah kesisi


</details>

<details>
<summary><b>HOW TO WORK WITH CONFIG</b></summary>

### Cloning
```bash
git clone --recurse-submodules https://gitlab.informatika.org/IF3110-2021-02-K03-02/eatsnow-config.git
```

### Pushing changes
1. go to the submodule directory first and checkout to main branch
```bash
cd eatsnow-config
git checkout main
```
2. then work in it like usual. After done, commit and push the submodule
```bash
git add .
git commit -m "message"
git push
```
3. then go back to the main directory (__config__)
```bash
cd ..
```
4. then push the main directory (__config__)
```bash
git add .
git commit -m "message"
git push
```


### Update Config / Pulling latest changes in submodule

```
git submodule update --recursive --remote
```

