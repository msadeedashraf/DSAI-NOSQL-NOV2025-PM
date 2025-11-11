# 🧠 MongoDB Query Operators — Practice Questions

These exercises help students understand **Comparison**, **Logical**, and **Evaluation** query operators in MongoDB.

---

## 🧱 Sample Dataset

Run this first in `mongosh` or your Atlas environment:

```js
use productsDB

db.items.insertMany([
  { name: "Laptop", category: "Electronics", price: 1200, stock: 5 },
  { name: "Mouse", category: "Electronics", price: 25, stock: 200 },
  { name: "Notebook", category: "Stationery", price: 5, stock: 500 },
  { name: "Backpack", category: "Bags", price: 45, stock: 50 },
  { name: "Monitor", category: "Electronics", price: 300, stock: 20 },
  { name: "Water Bottle", category: "Home & Kitchen", price: 12, stock: 150 }
])
```

---

## ❓ Question 1 — Comparison Operators

**Use `$gt`, `$lt`, and `$eq`:**

> Find all products in the `Electronics` category with a `price` greater than 100 and less than 1000.

💡 *Hint:* Combine multiple comparison operators within one field.

```js
db.items.find({ /* your query */ })
```

---

## ❓ Question 2 — Logical Operators

**Use `$or`:**

> Show all products that are **either** priced below 10 **or** have a `stock` greater than 300.

💡 *Hint:* `$or` takes an array of conditions.

```js
db.items.find({ /* your query */ })
```

---

## ❓ Question 3 — Logical `$and` and `$ne`

**Use `$and` and `$ne`:**

> Display all products that are **not** in the “Stationery” category **and** have a `price` greater than or equal to 40.

```js
db.items.find({ /* your query */ })
```

---

## ❓ Question 4 — Evaluation Operator `$regex`

**Use `$regex` (case-insensitive):**

> Find all products whose `name` starts with the letter “M”, ignoring case sensitivity.

💡 *Hint:* Use the `i` flag for case-insensitive matching.

```js
db.items.find({ /* your query */ })
```

---

## ❓ Question 5 — `$in` and `$text` Search

> 1. Create a text index on the `category` field.  
> 2. Search for all items where the category contains either “Electronics” or “Bags”.

💡 *You can use either `$in` for direct filtering or `$text` for a text-based search.*

```js
// Option 1: Using $in
db.items.find({ /* your query */ })

// Option 2: Using $text (requires text index)
db.items.createIndex({ category: "text" })
db.items.find({ /* your query */ })
```

---

## 💡 Bonus Challenge

> Use `$where` to find all products where `price < stock / 10`.

```js
db.items.find({ /* your query */ })
```

---