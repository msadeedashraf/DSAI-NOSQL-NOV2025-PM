### 

```
use shopDB

db.customers.drop(); db.orders.drop(); db.products.drop();

db.customers.insertMany([
  { _id: 1, name: "Ali",   city: "Toronto",   tier: "gold" },
  { _id: 2, name: "Sara",  city: "Ottawa",    tier: "silver" },
  { _id: 3, name: "John",  city: "Toronto",   tier: "bronze" }
]);

db.products.insertMany([
  { _id: 101, sku: "KB-01", name: "Keyboard",   category: "Electronics", price: 79.99 },
  { _id: 102, sku: "MS-01", name: "Mouse",      category: "Electronics", price: 25.00 },
  { _id: 103, sku: "NB-01", name: "Notebook",   category: "Stationery",  price: 5.00  }
]);

db.orders.insertMany([
  { _id: 1001, customerId: 1, items: [ { productId: 101, qty: 1 }, { productId: 102, qty: 2 } ], createdAt: ISODate("2025-10-01") },
  { _id: 1002, customerId: 2, items: [ { productId: 103, qty: 10 } ],                               createdAt: ISODate("2025-10-05") },
  { _id: 1003, customerId: 1, items: [ { productId: 102, qty: 1 } ],                                 createdAt: ISODate("2025-10-15") },
  { _id: 1004, customerId: 3, items: [ { productId: 101, qty: 1 }, { productId: 103, qty: 3 } ],     createdAt: ISODate("2025-11-01") }
]);

```


```
db.customers.aggregate([
  { $match: { city: "Toronto" } }
]);
```

```
db.orders.aggregate([  
		{
		$lookup: { 
			from :"customers", 
			localField: "customerId", 
			foreignField: "_id", 
			as : "customer" }} ,
 		{$unwind:"$customer"}  
	])


```
