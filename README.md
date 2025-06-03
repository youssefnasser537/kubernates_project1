# 🚀 Deploying WordPress & MySQL on Kubernetes with Persistent Volumes

هذا المشروع يوضح كيفية نشر موقع WordPress متصل بقاعدة بيانات MySQL على Kubernetes باستخدام:
- **Volumes دائمة (PVs + PVCs)**
- **Secrets لحماية البيانات الحساسة**
- **Services و NodePort للوصول الخارجي**

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
