# UTS Praktikum – Manajemen Jaringan

## Identitas Mahasiswa

* **Nama**: Najwa Kania
* **NIM**: 240104009

---

## Deskripsi Project

Project ini merupakan UTS Praktikum Manajemen Jaringan yang mengintegrasikan **Git, Docker, MySQL, PostgreSQL, Adminer, dan ZeroTier**. Fokus utama project adalah **isolasi network Docker** serta **kontrol akses database hanya melalui jaringan ZeroTier**.

---

## Konfigurasi Service

### 1. Container & Service

| Service    | Container Name |
| ---------- | -------------- |
| MySQL      | uts_mysql      |
| PostgreSQL | uts_postgres   |
| Adminer    | uts_adminer    |

---

### 2. Database Credential

#### MySQL

```
Database  : uts_mysql_db
Username  : uts_user
Password  : uts_password
Root Pass : root_uts
```

#### PostgreSQL

```
Database : uts_postgres_db
Username : uts_user
Password : uts_password
```

---

## Network Configuration

* **Docker Network**: `uts_internal_net`
* **Subnet**: `172.30.9.0/24`

### Static IP Address

| Container  | IP Address  |
| ---------- | ----------- |
| MySQL      | 172.30.9.10 |
| PostgreSQL | 172.30.9.20 |
| Adminer    | 172.30.9.30 |

---

## Adminer Access

* **Port Adminer**: `8009`
* **Akses**: hanya melalui jaringan **ZeroTier**

```
http://IP_ZEROTIER:8009
```

> Adminer tidak mengekspos port database ke publik dan hanya dapat diakses melalui ZeroTier sesuai ketentuan UTS.

---

## Cara Menjalankan Project

1. Clone repository:

```bash
git clone https://github.com/najwakania01/240104009-udb-uts.git
```

2. Masuk ke direktori project:

```bash
cd 240104009-udb-uts
```

3. Jalankan container:

```bash
docker compose up -d
```

4. Pastikan container berjalan:

```bash
docker ps
```

---

## Akses Database melalui Adminer

### Login MySQL

* System: MySQL / MariaDB
* Server: uts_mysql
* Username: uts_user
* Password: uts_password
* Database: uts_mysql_db

### Login PostgreSQL

* System: PostgreSQL
* Server: uts_postgres
* Username: uts_user
* Password: uts_password
* Database: uts_postgres_db

---

## Dokumentasi (Screenshot Wajib)

Lampirkan screenshot berikut:

1. ![Docker PS](screenshots/docker_ps.png)
2. ![Adminer Zerotier](screenshots/adminer_zerotier.png)
3. ![Login MySQL](screenshots/login_mysql.png)
4. ![Login PostgreSQL](screenshots/login_postgres.png)

---

## Kesimpulan

Project ini berhasil menerapkan isolasi network Docker serta pengamanan akses database menggunakan ZeroTier. MySQL dan PostgreSQL hanya dapat diakses secara internal oleh Adminer, sementara Adminer sendiri hanya dapat diakses melalui jaringan ZeroTier, sehingga memenuhi seluruh ketentuan UTS Praktikum Manajemen Jaringan.


