### **1. What are the four main principles of OOP?**
**Answer:**
The four main principles of OOP are:
1. **Encapsulation**: Bundling data and methods that operate on the data within a single unit (class) and restricting access to some of the object's components.
2. **Inheritance**: A mechanism where a new class derives properties and behavior from an existing class.
3. **Polymorphism**: The ability of objects to take on multiple forms (e.g., method overriding and method overloading).
4. **Abstraction**: Hiding complex implementation details and exposing only the necessary features.

---

### **2. What is the difference between a class and an object in C#?**
**Answer:**
- A **class** is a blueprint or template that defines the structure and behavior of objects. It contains fields, properties, methods, and events.
- An **object** is an instance of a class. It is a concrete entity created from the class blueprint.

Example:
```csharp
class Car { } // Class
Car myCar = new Car(); // Object
```

---

### **3. What is encapsulation, and how is it achieved in C#?**
**Answer:**
Encapsulation is the concept of bundling data (fields) and methods (functions) that operate on the data within a single unit (class) and controlling access to the data. In C#, encapsulation is achieved using:
- **Access modifiers** like `private`, `public`, `protected`, and `internal`.
- **Properties** to provide controlled access to private fields.

Example:
```csharp
class Person {
    private string name; // Private field
    public string Name { // Public property
        get { return name; }
        set { name = value; }
    }
}
```

---

### **4. What is inheritance, and how does it work in C#?**
**Answer:**
Inheritance is a mechanism where a new class (derived class) inherits properties and behavior from an existing class (base class). In C#, inheritance is achieved using the `:` symbol.

Example:
```csharp
class Animal { // Base class
    public void Eat() {
        Console.WriteLine("Eating...");
    }
}
class Dog : Animal { } // Derived class
```

---

### **5. What is polymorphism, and how is it implemented in C#?**
**Answer:**
Polymorphism allows objects to take on multiple forms. In C#, it is implemented using:
- **Method Overriding**: Using the `virtual` keyword in the base class and `override` in the derived class.
- **Method Overloading**: Defining multiple methods with the same name but different parameters.

Example of Method Overriding:
```csharp
class Animal {
    public virtual void Sound() {
        Console.WriteLine("Animal sound");
    }
}
class Dog : Animal {
    public override void Sound() {
        Console.WriteLine("Bark");
    }
}
```

---

### **6. What is abstraction, and how is it achieved in C#?**
**Answer:**
Abstraction is the concept of hiding complex implementation details and exposing only the necessary features. In C#, abstraction is achieved using:
- **Abstract classes**: Classes that cannot be instantiated and can contain abstract methods.
- **Interfaces**: Contracts that define a set of methods without implementation.

Example:
```csharp
abstract class Shape {
    public abstract void Draw(); // Abstract method
}
class Circle : Shape {
    public override void Draw() {
        Console.WriteLine("Drawing Circle");
    }
}
```

---

### **7. What is the difference between an abstract class and an interface in C#?**
**Answer:**
- **Abstract Class**:
  - Can have both abstract and non-abstract methods.
  - Can contain fields, properties, and constructors.
  - Supports access modifiers.
  - A class can inherit only one abstract class.
- **Interface**:
  - Can only have method signatures (no implementation until C# 8.0).
  - Cannot contain fields or constructors.
  - All members are public by default.
  - A class can implement multiple interfaces.

---

### **8. What is method overloading in C#?**
**Answer:**
Method overloading is the ability to define multiple methods with the same name but different parameters (type, number, or order). It is a form of compile-time polymorphism.

Example:
```csharp
class Math {
    public int Add(int a, int b) { return a + b; }
    public double Add(double a, double b) { return a + b; }
}
```

---

### **9. What is method overriding in C#?**
**Answer:**
Method overriding is the ability of a derived class to provide a specific implementation of a method that is already defined in its base class. It is achieved using the `virtual` keyword in the base class and the `override` keyword in the derived class.

Example:
```csharp
class Animal {
    public virtual void Sound() {
        Console.WriteLine("Animal sound");
    }
}
class Dog : Animal {
    public override void Sound() {
        Console.WriteLine("Bark");
    }
}
```

---

### **10. What is the difference between `virtual` and `abstract` methods in C#?**
**Answer:**
- **Virtual Method**:
  - Has a default implementation in the base class.
  - Can be overridden in the derived class using the `override` keyword.
- **Abstract Method**:
  - Does not have an implementation in the base class.
  - Must be overridden in the derived class.

---

### **11. What is a sealed class in C#?**
**Answer:**
A sealed class is a class that cannot be inherited. It is defined using the `sealed` keyword.

Example:
```csharp
sealed class Animal { }
// class Dog : Animal { } // Error: Cannot inherit from sealed class
```

---

### **12. What is a constructor, and what are its types in C#?**
**Answer:**
A constructor is a special method used to initialize an object. Types of constructors in C# include:
1. **Default Constructor**: No parameters.
2. **Parameterized Constructor**: Takes parameters.
3. **Static Constructor**: Initializes static members.
4. **Copy Constructor**: Initializes an object using another object of the same class.

Example:
```csharp
class Person {
    public Person() { } // Default constructor
    public Person(string name) { } // Parameterized constructor
}
```

---

### **13. What is the difference between `struct` and `class` in C#?**
**Answer:**
- **Class**:
  - Reference type.
  - Supports inheritance.
  - Can have a destructor.
- **Struct**:
  - Value type.
  - Does not support inheritance.
  - Cannot have a destructor.

---

### **14. What is the `this` keyword in C#?**
**Answer:**
The `this` keyword refers to the current instance of the class. It is used to:
- Differentiate between class fields and parameters with the same name.
- Pass the current object as a parameter to another method.

Example:
```csharp
class Person {
    private string name;
    public Person(string name) {
        this.name = name; // 'this' refers to the current instance
    }
}
```

---

### **15. What is the `base` keyword in C#?**
**Answer:**
The `base` keyword is used to access members of the base class from within a derived class. It is commonly used to call the base class constructor.

Example:
```csharp
class Animal {
    public Animal(string name) { }
}
class Dog : Animal {
    public Dog(string name) : base(name) { } // Calls base class constructor
}
```

---

### **16. What is a destructor in C#?**
**Answer:**
A destructor is a special method used to release unmanaged resources before an object is destroyed. It is defined using the `~` symbol.

Example:
```csharp
class Person {
    ~Person() { // Destructor
        // Cleanup code
    }
}
```

---

### **17. What is the difference between `is` and `as` operators in C#?**
**Answer:**
- **`is`**: Checks if an object is of a specific type and returns a boolean.
- **`as`**: Attempts to cast an object to a specific type and returns `null` if the cast fails.

Example:
```csharp
if (obj is Person) { } // 'is' operator
Person p = obj as Person; // 'as' operator
```

---

### **18. What is a partial class in C#?**
**Answer:**
A partial class allows a class definition to be split across multiple files. It is defined using the `partial` keyword.

Example:
```csharp
// File1.cs
partial class Person {
    public void Method1() { }
}
// File2.cs
partial class Person {
    public void Method2() { }
}
```

---

### **19. What is a static class in C#?**
**Answer:**
A static class is a class that cannot be instantiated and can only contain static members. It is defined using the `static` keyword.

Example:
```csharp
static class Math {
    public static int Add(int a, int b) { return a + b; }
}
```

---

### **20. What is the difference between `IEnumerable` and `IQueryable` in C#?**
**Answer:**
- **`IEnumerable`**:
  - Used for in-memory collections.
  - Executes queries on the client side (LINQ to Objects).
- **`IQueryable`**:
  - Used for querying data from out-of-memory sources (e.g., databases).
  - Executes queries on the server side (LINQ to Entities).

