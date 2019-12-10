# *代码仅仅是思想的一种体现*

- 当成员变量和局部变量重名，可以用关键字this来区分；

- this也可以用于在构造函数中调用其他构造函数，但是this语句要放在构造函数第一行；

- static 修饰的成员既可以直接被对象调用，也可以直接被类名调用(修饰的成员被所有对象共享)

- static优先于对象存在，因为它修饰的成员在类的加载时就已经存在；

- 成员变量---实例变量    静态变量----类变量

- person是一个类   person  xw   这里的xw是类类型变量

- 静态变量数据存储在方法区（静态区）对象

- **静态方法只能访问静态成员（但是非静态可以访问静态）**

- **静态方法中不可以使用this或者super关键字**

- static关键字修饰的方法可以视为类方法，不需要创建对象就可以直接调用该方法。（用该方法所属类名直接调用）

- ------
  
  ```java
  static{
     //********
  }
  静态代码块随着类的加载执行一次（用于给类进行初始化）
  
  
  {    构造代码块，给所有对象初始化
  //*******
  }
  ```
  
  
