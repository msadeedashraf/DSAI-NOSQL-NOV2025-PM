# 🧠 MongoDB 101 — Beginner’s Hands-On Tutorial

## 🎯 Learning Goals
By the end of this tutorial, you’ll be able to:
- Understand what MongoDB is and how it stores data  
- Set up MongoDB using **Atlas Cloud**, **Compass GUI**, and **Mongo Shell**  
- Create your first **database**, **collections**, and **documents**  
- Perform **CRUD** operations (Create, Read, Update, Delete)  
- Learn essential MongoDB commands for beginners  

---

## 🧩 1. What Is MongoDB?

MongoDB is a **NoSQL database** — it stores data in **documents (JSON-like format)** instead of traditional tables.

Example document:

```json
{
  "name": "Alex",
  "age": 35,
  "city": "Toronto"
}
```

- A **Database** is like a folder.  
- A **Collection** is like a table inside that folder.  
- A **Document** is like a record or row (but in JSON form).

---

## ☁️ 2. Setup MongoDB Atlas (Cloud)

1. Go to [https://www.mongodb.com/cloud/atlas](https://www.mongodb.com/cloud/atlas)
2. Click **Sign Up** (use Google or Email)
3. Create a **Free Cluster (Shared Tier)**
   - Choose provider: *AWS / Azure / GCP*
   - Region: pick one near you (e.g., *Canada East*)
4. Under **Database Access → Add New Database User**
   - Username: `student`
   - Password: `Pass1234` (for demo)
5. Under **Network Access → Add IP Address**
   - Choose **Allow access from anywhere (0.0.0.0/0)** for now
6. Once cluster is ready → click **Connect → Connect using MongoDB Compass**

---

## 🖥️ 3. Setup MongoDB Compass (GUI Tool)

1. Download Compass: [https://www.mongodb.com/try/download/compass](https://www.mongodb.com/try/download/compass)
2. Open Compass → paste your **Atlas connection string**, e.g.:

   ```
   mongodb+srv://student:Pass1234@cluster0.mongodb.net/
   ```

   💡 If your password has symbols, encode them like `%40` for `@`.

3. Click **Connect** → you’ll see your cluster and databases.

---

## 💻 4. Setup MongoDB Shell (mongosh)

1. Install Mongo Shell (if not included with Compass):  
   [https://www.mongodb.com/try/download/shell](https://www.mongodb.com/try/download/shell)
2. Open terminal and connect:

   ```bash
   mongosh "mongodb+srv://student:Pass1234@cluster0.mongodb.net/"
   ```

3. You are now connected!  
   The prompt looks like:
   ```
   Atlas test>
   ```

---
