# C# note

NhanNguyen

some little note by myself to remind what did i learn

---

## Things worth to review:

| No. | Content                                   |
| --- | ----------------------------------------- |
|     |                                           |
| 1   | [Overview - Basic](#section-01-the-basic) |
|     | [Namespace](#namespace)                   |
| 2   | [Class](#class)                           |
| 3   | [Unit Test](#unit-test)                   |

# Section 01 - THE BASIC

We write `C#` in IDE and under the hood when we run `dotnet run`, `C# Compiler (.NET (SDK))` will compile our code to binary code which called `assembly` is contained in `dll file (Dynamic Link Library)`

<img src="./img/1.PNG" width="900">

<img src="./img/2.PNG" width="900">

## Namespace

`Namespace` is where we declare our `class` and `method` of class.

It create it own scope and prevent `name conflict` of `class` inside our project and in other library

    `List<>() class` is created in System.Collections.Generic Namespace
    `Console.WriteLine()` is created in System Namespace`

### Best practice: There are should only one class in one file

## Class

Section 4

Class is a blueprint - it contain our property and method.

When we use `new keyword` and `() operator`. C# implicitly call `Constructor()` method.

### Why we you class?

1. Because we want to `encapsulate` and `abstract` our `class`, so that when `other developer` or `us` in the future can `understand quickly` what we are doing

2. Because we want to provide some abstraction and some encapsulation to hide the complexity of this class
   => Easy to maintaining and readable

**Encapsulation:**: is hiding complexities and hiding details that are unimportant at a high level of view

### Static - Public - Private

**Public**: mean that, if we want to use this public property or method inside a class. We have to instantiate an instance of this class

**Private**: mean that this private property or method only accessible inside this class

**Static**: mean that we only have access to this static property or method through this class, not through the instances object of this class

    WriteLine method in Console class of System namespace is static

**Internal**: mean that this class can only be used in the same project

---

---

# Unit Test

Unit test is do the testing for unit part of our code

We use `Xunit` to do the unit test

There are 3 section of unit test

- `Arrange`: Where we put all our test data and we arrange value we going to use

- `Act`: Where we perform calculation to perform actual result

- `Assert`: Where we assert something about the Actual value in Act

# Reference And Value Type

## Variable and Value Type

Variable only can hold value

## Reference Type

Meaning the variable hold a value address that reference to where the instances object (create by class) stay inside the memory.

## Value Type

Meaning variable actual hold the value sit in memory

## Pass by value

In `C#` and `JavaScript` we pass parameter into method by value

=> It mean when we pass object variable as parameter => We pass the address value of that variable for the parameter
=> Both variable and passed parameter hold the same address that point to the same Object Value stay in the memory

## Pass by reference

It mean we pass the reference of the variable to parameter => The parameter is reference to that variable not the actual - underlying value sit in memory

## String are reference but it not be immutable

# Garbage Collection

When a value is not reference to any value or out of scope, it will be automatically garbage collect and it no longer take place in memory.

---

---

# ASP.NET CORE

## SQL Verb and HTTP Verb

<img src="./img/3.PNG" width="900">

## Model - View - Controller (MVC)

`Model` is responsible for direct connect to database. Get or Put data from database when `Controller` ask.

`View` contain HTML/CSS code that dynamic receive data from database through `Controller` ( with the help of front-end framework ) - This piece of HTML/CSS is send back to `Controller` to display UI for User

`Controller` is middleman - receive `User` input and pass it to `Model` - receive respond from `Model` and pass data to `View` - receive HTML/CSS code from `View` and display it to UI

<img src="./img/4.PNG" width="900">

## ORM (Object relational mapper) - Entity Framework

`Object relational mapping` is a technique to convert` object-class data` to `relational database (tables)` by `Data layer`

### Code first - Database first

`Code First`: mean that we write code in `Model Class` and ask `Entity Framework` to convert our code to `Databases/Tables`

## Step by step to run a .NET api with code first

Step-by-step: 
	Dotnet ef migration add 'migration name' => To create entities and table
	Dotnet ef database update => To update it to database
	Dotnet ef database drop => To drop all database
	Dotnet ef migration remove => To remove one previous migraiton
To Remove All Migration:
	Remove folder migrations in our project
	Add new migrations
Update database