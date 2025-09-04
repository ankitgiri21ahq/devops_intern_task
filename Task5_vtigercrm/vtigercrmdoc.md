

# 📘 Vtiger CRM Installation Guide (Using Docker & Docker Compose)

This guide provides step-by-step instructions to install **Vtiger CRM 8.2.0** using Docker and Docker Compose. 
It sets up two containers:

- **MariaDB (Database)**
- **Vtiger CRM (Apache + PHP)**

--- 

## 🧱 Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed on your system.
- [Docker Compose](https://docs.docker.com/compose/install/) installed.
- Code editor (e.g., Visual Studio Code).

---

## 📂 Step 1: Create Project Directory

Open **VS Code** or your terminal and create a new folder:

```bash
mkdir vtiger
cd vtiger
mkdir vtiger-unified
cd vtiger-unified
````

---

## 📄 Step 2: Create the `docker-compose.yml` File

Run the following command to create the Docker Compose configuration file:

```bash
nano docker-compose.yml
```

### Paste the following content into the file:

```yaml
version: "3.9"

services:
  db:
    image: mariadb:10.6
    container_name: vtiger_db
    environment:
      MYSQL_ROOT_PASSWORD: rootpass
      MYSQL_DATABASE: vtiger
      MYSQL_USER: vtiger
      MYSQL_PASSWORD: vtigerpass
    volumes:
      - vtiger_mysql_data_volume:/var/lib/mysql
    restart: unless-stopped

  vtiger:
    image: vtigercrm/vtigercrm-8.2.0:latest
    container_name: vtiger_app
    depends_on:
      - db
    ports:
      - "8080:80" # Access CRM via http://localhost:8080
    volumes:
      - vtiger_source_volume:/var/www/html/
    restart: unless-stopped

volumes:
  vtiger_source_volume:
  vtiger_mysql_data_volume:
```

---

## 🧾 Configuration Explanation

### Services:

* **`db`**: Runs a MariaDB container (MySQL-compatible).
* **`vtiger`**: Runs the Vtiger CRM application (Apache + PHP).

### Volumes:

* **`vtiger_source_volume`**: Stores web files of Vtiger (persistent).
* **`vtiger_mysql_data_volume`**: Stores MySQL data (persistent).

### Ports:

* **8080:80**: Exposes Vtiger on `http://localhost:8080`.

---

## ▶️ Step 3: Start the Containers

Run the following command:

```bash
docker compose up -d
```

### Explanation:

* **`docker compose`**: Reads the `docker-compose.yml` file.
* **`up`**: Creates and starts the containers.
* **`-d`**: Runs in detached (background) mode.

This command starts two containers:

* `vtiger_db` → MariaDB
* `vtiger_app` → Apache + PHP + Vtiger CRM

And two volumes:

* `vtiger_source_volume`
* `vtiger_mysql_data_volume`

---

## 📋 Step 4: Check Running Containers

```bash
docker compose ps
```

This shows the status of the running containers.

---

## 🧪 Step 5: Verify MySQL Inside the Container

Your local MySQL (e.g., installed via Homebrew) will not show the Vtiger database. That’s because the database is created **inside the Docker container**.

To access it:

```bash
docker compose exec db mysql -u root -p
```

* **Password**: `rootpass` (as defined in `docker-compose.yml`)

Inside the MySQL prompt, type:

```sql
SHOW DATABASES;
```

You should see `vtiger` listed.

---

## ⚙️ Step 6: Complete Web-Based Installation

Open your browser and navigate to:

```
http://localhost:8080
```

### Database Configuration Page:

Enter the following:

* **Database Type**: MySQL
* **Host Name**: `db`
* **Database Name**: `vtiger`
* **Username**: `vtiger`
* **Password**: `vtigerpass`

(These match the environment variables in `docker-compose.yml`.)

### Admin User Setup:

Fill in admin account details as required on the installation screen.

---

## 🧹 Step 7: Manage Containers

### Stop and Remove Containers:

```bash
docker compose down
```

* Stops and removes containers.
* **Volumes are preserved**, so data and installation remain intact.

### Restart Containers:

```bash
docker compose up -d
```

* Since volumes are still available, the CRM will skip the installation wizard and take you directly to the **login page**.

### Check Status:

```bash
docker compose ps
```

---

## 🛑 Optional: Stop/Start Without Removing

To **stop** the containers without removing them:

```bash
docker compose stop
```

To **start** them again:

```bash
docker compose start
```

---

## 📜 Logs (Debugging)

To view real-time logs from a container:

```bash
docker compose logs -f vtiger
```

Or for the database container:

```bash
docker compose logs -f db
```

---

## ✅ Installation Complete

Your Vtiger CRM setup is now ready and accessible at:

```
http://localhost:8080
```

You can now log in using the admin credentials you created.

```

Let me know if you'd like a version without emojis or if you want this localized into a different style!
```
---

<pre>
Database service (db):

  db:
    image: mariadb:10.6
    container_name: vtiger_db


Runs a MariaDB database (like MySQL).
Container name = vtiger_db.


Qn.Why MariaDB in your file?
VtigerCRM needs a MySQL-compatible database.
MariaDB is a drop-in replacement for MySQL → faster, open-source, and lighter.
That’s why most Docker examples use MariaDB (instead of Oracle’s MySQL).


Qn.Can you change container name?
Yes ✅
container_name: vtiger_db
container_name: my_custom_db

or even remove it → then Docker will auto-generate a name (like projectname_db_1).



Qn.How to do this in AWS?

Option 1: Simple EC2 (easy for testing/study)
Launch an EC2 instance (Ubuntu or Amazon Linux).
Choose t2.medium or larger (2GB+ RAM).
Install Docker + Docker Compose:

sudo apt update && sudo apt install docker.io docker-compose -y
sudo systemctl enable docker && sudo systemctl start docker

Copy your docker-compose.yml to the server.
docker compose up -d

Open EC2 Security Group → allow inbound traffic on port 8080.


Option 2: AWS ECS (production ready)
Instead of running containers manually, use ECS (Elastic Container Service).
Steps:
Push your images (or just use vtigercrm/vtigercrm-8.2.0) to Amazon ECR.
Create an ECS Cluster.
Define Tasks:
Task 1 = MariaDB
Task 2 = Vtiger
Use Fargate (serverless) or EC2-backed ECS to run them.
Add a Load Balancer for Vtiger frontend (port 80/8080).
Use RDS (MySQL/MariaDB) instead of running DB inside container (safer, managed backups).


Option 3: Hybrid (recommended for startups)
Run Vtiger in Docker on EC2.
Use AWS RDS (MariaDB/MySQL) for database (scalable, automatic backups).

Structure -
User → ALB (Load Balancer) → EC2 (Docker: Vtiger)
                        ↘
                         RDS (MariaDB)

✅ Summary
You use MariaDB because Vtiger needs MySQL-compatible DB.
You can switch to MySQL/Percona if you want.
Yes, container names can be changed.
On AWS:
For learning → EC2 + Docker is easiest.
For production → ECS + RDS is better.

</pre>
