# 🚀 Deploying WordPress & MySQL on Kubernetes with Persistent Volumes

This project demonstrates how to deploy a WordPress website connected to a MySQL database on Kubernetes using:

- **Persistent Volumes (PVs & PVCs)**
- **Secrets for protecting sensitive data**
- **Services and NodePort for external access**

---

## 🧩 Architecture Overview

```plaintext
                +----------------------------+
                |       External Users       |
                +-------------+--------------+
                              |
                              | HTTP (NodePort 30080)
                              ▼
                    +-------------------+
                    |  WordPress Pod    |
                    |-------------------|
                    | Persistent Volume |
                    +--------+----------+
                             |
                             | MySQL DB Credentials (Secret)
                             ▼
                    +-------------------+
                    |   MySQL Pod       |
                    |-------------------|
                    | Persistent Volume |
                    +-------------------+

