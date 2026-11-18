# ☁️ Full-Stack Cloud Migration to AWS (Server, App & DB)

An end-to-end enterprise cloud migration project demonstrating the seamless lift-and-shift and re-platforming of an on-premises workload—including **virtual servers, web applications, and relational databases**—onto a secure, highly available **Amazon Web Services (AWS)** environment.

---

## 🏗️ Migration Architecture & Phases

### 1. Network & Security Foundation (Amazon VPC)
- Designed a custom **Amazon VPC** segmented into **Public Subnets** (for web/bastion access) and **Private Subnets** (for isolated database and backend tiers).
- Configured **Internet Gateway (IGW)**, **NAT Gateway**, custom **Route Tables**, and granular **Security Groups** to enforce strict network isolation.

### 2. Server & Application Migration (AWS MGN & EC2)
- Utilized **AWS Application Migration Service (AWS MGN)** to replicate on-premises virtual machine disks to AWS with continuous block-level data replication.
- Configured launch templates and cutover instances to migrate the Linux server and application runtime onto **Amazon EC2** with minimal downtime.
- Verified application dependencies, web server configurations, and service health post-cutover.

### 3. Database Migration & Replication (AWS DMS & Amazon RDS)
- Migrated an on-premises **PostgreSQL** database to a managed **Amazon RDS for PostgreSQL** instance deployed inside a private subnet.
- Configured **AWS Database Migration Service (DMS)** replication instances, source/target endpoints, and migration tasks using **Full Load + Change Data Capture (CDC)** for continuous synchronization.
- Validated schema integrity, table row counts, and application-to-database connectivity using **pgAdmin**.

### 4. Monitoring, Validation & Cutover
- Integrated **Amazon CloudWatch** metrics and alarms to monitor EC2 CPU/memory utilization, RDS performance, and DMS replication lag.
- Conducted end-to-end functional testing and DNS/traffic cutover to verify zero data loss.

---

## 🛠️ AWS Services & Tech Stack Used

- **Migration Services:** AWS Application Migration Service (MGN), AWS Database Migration Service (DMS)
- **Compute & Networking:** Amazon EC2, Amazon VPC, Subnets, Route Tables, NAT Gateway, Internet Gateway, Security Groups
- **Database:** Amazon RDS (PostgreSQL), pgAdmin
- **Operating System:** Red Hat Enterprise Linux (RHEL) / Amazon Linux
- **Security & Monitoring:** AWS IAM, Amazon CloudWatch

---

## ✨ Key Highlights & Outcomes

- **Minimal Downtime Migration:** Leveraged continuous replication (MGN) and CDC (DMS) to keep source and target environments synchronized prior to final cutover.
- **Enhanced Security Posture:** Moved the database layer from an exposed local setup into isolated AWS private subnets protected by stateful security groups and IAM roles.
- **Managed Operations:** Offloaded routine database patching, automated backups, and hardware maintenance by transitioning to Amazon RDS.
