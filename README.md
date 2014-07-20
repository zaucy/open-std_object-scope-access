Object Scope Access
============================

Instead of accessing a member of an object with `object.member` you can instead use `object.{ /* use members here */ }` this creates a scope just like you would with `{}` but the object's members are exposed.

```c++
class Object {
public:
  void doSomething(int withThis);
};

// ...

Object obj;

obj.{
  int n = 12;
  doSomething(n);
}
```

Creating a variable within the object scope does not create the variable within the objects scope. The above would be the same as this...

```c++
Object obj;

{
  int n = 12;
  obj.doSomething(n);
}
```

Accessing an objects scope is just another way to create a scope. Therefore you can use it with `if`, `else`, `for`, `while`, `switch` or even functions and lambdas. (Feeling wishy washy about this part)

```c++
Object obj;

if(100 > 10) obj.{
  // ...
} else obj.{
  // ...
}

while(true) obj.{
  // ...
}

for(int i=0; i > 100; i++) obj.{
  
}

switch(10) obj.{
case 10:
  // ...
default:
  // ...
}

void doCoolThings() obj.{
  
}

[] obj.{
  
}
```

