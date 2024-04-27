# **PENUGASAN 2 AJK**
Nama : Jericho Nathanael Chrisnantha

NRP  : 5025221001

---
## **Tugas**
Melakukan konfigurasi ansible untuk melakukan deployment front-end dan juga back-end.

---
## **Langkah-Langkah Pengerjaan**

Inisialisasi roles dengan perintah :

```bash
ansible-galaxy init NAMA_ROLES
```

Roles yang akan dibuat adalah sebagai berikut :

- **nginx-prepare**     : Melakukan instalasi nginx, mengatur beberapa port yang nanti akan digunakan, dana memulai service nginx.

- **mysql-prepare**     : Melakukan instalasi mySQL dan membuat DB user.

- **backend-build**     : Melakukan instalasi PHP + composer dan melakukan clone pada repository BE yang sudah disediakan.

- **backend-migrate**   : Melakukan migrasi BE dan menghasilkan app key dan JWT secret.

- **backend-deploy**    : Mendeploy BE, termasuk menyalin template BE ke konfigurasi Nginx dan melakuakn pengujian dengan `curl`.

- **frontend-build**    : Melakukan instalasi NVM, Yarn, Node.js, npm, pm2 dan melakukan build pada FE  menggunakan Yarn.

- **frontend-deploy**    : Mendeploy FE, termasuk menyalin template FE ke konfigurasi Nginx dan melakukan pengujian dengan `curl`.

Semua roles diatas akan dijalankan pada playbooks sesuai dengan suffix masing-masing role. Kemudian playbooks [prepare.yml](/playbooks/prepare.yml), [build.yml](/playbooks/build.yml), [migrate.yml](/playbooks/migrate.yml), dan [deploy.yml](/playbooks/deploy.yml) akan dijalankan pada playbook [main.yml](/playbooks/main.yml) dengan menggunakan perintah :

```bash
ansible-playbook main.yml
```