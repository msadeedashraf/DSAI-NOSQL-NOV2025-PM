Microsoft Windows [Version 10.0.22621.4317]
(c) Microsoft Corporation. All rights reserved.

C:\Windows\System32>mongosh
Current Mongosh Log ID: 69127427f964622ddbcdcdf5
Connecting to:          mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+2.2.6
Using MongoDB:          7.0.11
Using Mongosh:          2.2.6
mongosh 2.5.9 is available for download: https://www.mongodb.com/try/download/shell

For mongosh info see: https://docs.mongodb.com/mongodb-shell/

------
   The server generated these startup warnings when booting
   2025-11-10T05:24:32.759-05:00: Access control is not enabled for the database. Read and write access to data and configuration is unrestricted
------

test> show dbs
admin        40.00 KiB
config       84.00 KiB
cook        244.00 KiB
local       100.00 KiB
monkeys-db   72.00 KiB
mydatabase  128.00 KiB
test> use monkeys-db
switched to db monkeys-db
monkeys-db>

monkeys-db>

monkeys-db> use student_portal
switched to db student_portal
student_portal> db.students.insertMany([  { name: "Ali", age: 20, city: "Toronto", grade: 85, program: "CS" },    ])
{
  acknowledged: true,
  insertedIds: { '0': ObjectId('691274a5f964622ddbcdcdf6') }
}
student_portal>   { name: "Sara", age: 22, city: "Ottawa", grade: 91, program: "Business" },
...   { name: "John", age: 19, city: "Toronto", grade: 70, program: "CS" },
...   { name: "Maria", age: 24, city: "Brampton", grade: 88, program: "Math" },
...
...
...
...
...
...
student_portal> db.students.find()
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  }
]
student_portal>

student_portal>

student_portal> db.students.insertMany([
...   { name: "Ali", age: 20, city: "Toronto", grade: 85, program: "CS" },
...   { name: "Sara", age: 22, city: "Ottawa", grade: 91, program: "Business" },
...   { name: "John", age: 19, city: "Toronto", grade: 70, program: "CS" },
...   { name: "Maria", age: 24, city: "Brampton", grade: 88, program: "Math" },
...   { name: "Omar", age: 21, city: "Toronto", grade: 65, program: "CS" }
... ])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('69127532f964622ddbcdcdf7'),
    '1': ObjectId('69127532f964622ddbcdcdf8'),
    '2': ObjectId('69127532f964622ddbcdcdf9'),
    '3': ObjectId('69127532f964622ddbcdcdfa'),
    '4': ObjectId('69127532f964622ddbcdcdfb')
  }
}
student_portal> db.students.find()
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf8'),
    name: 'Sara',
    age: 22,
    city: 'Ottawa',
    grade: 91,
    program: 'Business'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfa'),
    name: 'Maria',
    age: 24,
    city: 'Brampton',
    grade: 88,
    program: 'Math'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({city:{$eq: "Ottawa" }})
[
  {
    _id: ObjectId('69127532f964622ddbcdcdf8'),
    name: 'Sara',
    age: 22,
    city: 'Ottawa',
    grade: 91,
    program: 'Business'
  }
]
student_portal> db.students.find({city:{$eq: "Toronto" }})
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({grade:{$gt: 80 }})
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf8'),
    name: 'Sara',
    age: 22,
    city: 'Ottawa',
    grade: 91,
    program: 'Business'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfa'),
    name: 'Maria',
    age: 24,
    city: 'Brampton',
    grade: 88,
    program: 'Math'
  }
]
student_portal> db.students.find({grade:{$gt: 80 }})
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf8'),
    name: 'Sara',
    age: 22,
    city: 'Ottawa',
    grade: 91,
    program: 'Business'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfa'),
    name: 'Maria',
    age: 24,
    city: 'Brampton',
    grade: 88,
    program: 'Math'
  }
]
student_portal> db.students.find({city:{$eq: "toronto" }})

student_portal> db.students.find({city:{$eq: "Toronto" }})
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({grade:{$gte: 85 }})
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf8'),
    name: 'Sara',
    age: 22,
    city: 'Ottawa',
    grade: 91,
    program: 'Business'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfa'),
    name: 'Maria',
    age: 24,
    city: 'Brampton',
    grade: 88,
    program: 'Math'
  }
]
student_portal> db.students.find({age:{$lt: 21 }})
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  }
]
student_portal> db.students.find({age:{$lte: 70 }})
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf8'),
    name: 'Sara',
    age: 22,
    city: 'Ottawa',
    grade: 91,
    program: 'Business'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfa'),
    name: 'Maria',
    age: 24,
    city: 'Brampton',
    grade: 88,
    program: 'Math'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({program:{'CS': "Math" }})

student_portal> db.students.find({program:{ $in ['CS', "Math"] }})
Uncaught:
SyntaxError: Unexpected token, expected "," (1:32)

> 1 | db.students.find({program:{ $in ['CS', "Math"] }})
    |                                 ^
  2 |

student_portal> db.students.find({program:{ $in: ['CS', "Math"] }})
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfa'),
    name: 'Maria',
    age: 24,
    city: 'Brampton',
    grade: 88,
    program: 'Math'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({program:{ $nin: ['CS', "Math"] }})
[
  {
    _id: ObjectId('69127532f964622ddbcdcdf8'),
    name: 'Sara',
    age: 22,
    city: 'Ottawa',
    grade: 91,
    program: 'Business'
  }
]
student_portal> use abc
switched to db abc
abc> show dbs
admin            40.00 KiB
config          108.00 KiB
cook            244.00 KiB
local           100.00 KiB
monkeys-db       72.00 KiB
mydatabase      128.00 KiB
student_portal   72.00 KiB
abc>

abc>

abc>

abc>

abc>

abc> switch to db monkey-db
Uncaught:
SyntaxError: Unexpected token, expected "(" (1:7)

> 1 | switch to db monkey-db
    |        ^
  2 |

abc> switch db monkey-db
Uncaught:
SyntaxError: Unexpected token, expected "(" (1:7)

> 1 | switch db monkey-db
    |        ^
  2 |

abc> switch monkey-db
Uncaught:
SyntaxError: Unexpected token, expected "(" (1:7)

> 1 | switch monkey-db
    |        ^
  2 |

abc> use student_portal
switched to db student_portal
student_portal>

student_portal>

student_portal> db.students.find()
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf8'),
    name: 'Sara',
    age: 22,
    city: 'Ottawa',
    grade: 91,
    program: 'Business'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfa'),
    name: 'Maria',
    age: 24,
    city: 'Brampton',
    grade: 88,
    program: 'Math'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({ $and : [ age: 21,]})
Uncaught:
SyntaxError: Unexpected token, expected "," (1:31)

> 1 | db.students.find({ $and : [ age: 21,]})
    |                                ^
  2 |

student_portal>     city: 'Toronto'
Toronto
student_portal> db.students.find({ $and : { program:"CS" } , {city:"Brampton"}   )
Uncaught:
SyntaxError: Unexpected token (1:45)

> 1 | db.students.find({ $and : { program:"CS" } , {city:"Brampton"}   )
    |                                              ^
  2 |

student_portal> db.students.find({ $and : { program:"CS" } , {city:"Brampton"}  } )
Uncaught:
SyntaxError: Unexpected token (1:45)

> 1 | db.students.find({ $and : { program:"CS" } , {city:"Brampton"}  } )
    |                                              ^
  2 |

student_portal> db.students.find({ $and :[ { program:"CS" } , {city:"Brampton"}]  } )

student_portal> db.students.find({ $and :[ { program:"Maths" } , {city:"Brampton"}]  }
...
...
student_portal> db.students.find({ $and :[ { program:"Maths" } , {city:"Brampton"}]  }
...
...
...
...
student_portal> db.students.find({ $and :[ { program:"Math" } , {city:"Brampton"}]  }
...
student_portal> db.students.find({ program:"Math", city:"Brampton"} }
Uncaught:
SyntaxError: Unexpected token, expected "," (1:52)

> 1 | db.students.find({ program:"Math", city:"Brampton"} }
    |                                                     ^
  2 |

student_portal> db.students.find({ program:"Math", city:"Brampton"} )
[
  {
    _id: ObjectId('69127532f964622ddbcdcdfa'),
    name: 'Maria',
    age: 24,
    city: 'Brampton',
    grade: 88,
    program: 'Math'
  }
]
student_portal> db.students.find({
...   $and: [
...     { program: "CS" },
...     { city: "Toronto" }
...   ]
... })
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({
...   $and: [
...     { program: "CS" },
...     { city: "Toronto" }
...   ]
... })
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({
...   $and: [
...     { program: "CS" },
...     { city: "Toronto" }
...   ]
... })
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({
...   $and: [
...     { program: "CS" },
...     { city: "Toronto" }
...   ]
... })
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({
...   $and: [
...     { program: "CS" },
...     { city: "Toronto" }
...   ]
... })
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({$and:
... [
... {age: 20},
... {city: "Toronto"},
... {grade: 85}
... ]})
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  }
]
student_portal> db.students.find({$or:
... [
... {age: 20},
... {city: "Toronto"},
... {grade: 85}
... ]})
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({ $or: [ { city: "Toronto" }, { grade:{$gt: 85} }] })
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf8'),
    name: 'Sara',
    age: 22,
    city: 'Ottawa',
    grade: 91,
    program: 'Business'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfa'),
    name: 'Maria',
    age: 24,
    city: 'Brampton',
    grade: 88,
    program: 'Math'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal> db.students.find({ $nor: [ { city: "Toronto" }, { grade:{$gt: 90} }] })
[
  {
    _id: ObjectId('69127532f964622ddbcdcdfa'),
    name: 'Maria',
    age: 24,
    city: 'Brampton',
    grade: 88,
    program: 'Math'
  }
]
student_portal> db.students.find({ grade: { $gt: 90 } })
[
  {
    _id: ObjectId('69127532f964622ddbcdcdf8'),
    name: 'Sara',
    age: 22,
    city: 'Ottawa',
    grade: 91,
    program: 'Business'
  }
]
student_portal> db.students.find({ grade: {$not : { $gt: 90}  } })
[
  {
    _id: ObjectId('691274a5f964622ddbcdcdf6'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf7'),
    name: 'Ali',
    age: 20,
    city: 'Toronto',
    grade: 85,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdf9'),
    name: 'John',
    age: 19,
    city: 'Toronto',
    grade: 70,
    program: 'CS'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfa'),
    name: 'Maria',
    age: 24,
    city: 'Brampton',
    grade: 88,
    program: 'Math'
  },
  {
    _id: ObjectId('69127532f964622ddbcdcdfb'),
    name: 'Omar',
    age: 21,
    city: 'Toronto',
    grade: 65,
    program: 'CS'
  }
]
student_portal>