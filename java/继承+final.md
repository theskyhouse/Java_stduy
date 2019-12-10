# 代码仅仅是思想的一种体现

- java不**直接**支持多继承

- ```java
  class a{
  void show();
  }
  class b{
  void show();
  }
  class c extends a,b{}
  new c.show();//这里就出现问题了
  ```

  ------

  

this：代表本类对象引用；super：代表父类空间（不需要父类对象）

###### *在子类构造函数中第一行有一个隐式语句super(); //调用父类中空参数的构造函数*

**如果父类中没有定义空参数构造函数，那么子类的构造函数 必须用super明确调用父类哪个构造函数，同时子类构造函数中如果用this调用本类构造函数 super就没有了 super和this都只能定义在第一行 因此只能有一个（super语句必须定义在子类构造函数第一行）**

（super用法和this相似）

------

重写

1. 子类方法重写父类方法时，权限必须要大于等于父类权限。
2. 静态方法只能重写静态，非静态重写非静态
3. 构造方法不能被继承

------

```java
import java.util.*;
class  Father{
    Father(){
        super();
        show();//这里的show是子类中的=。=为什么呢？因为是拿父类的构造方法对子类进行初始化  指向子类
    }
    void show(){
        System.out.println("show father");
    }
}
class Son extends Father{
    int num=8;
    Son(){
        super();//通过super初始化父类内容时，子类成员变量未显示初始化（num=0）等父类初始化完后才显示初始化（super；只是把父类构造器的代码复制下来也可以是拿父类构造方法对子类进行初始化）
        System.out.println("show num "+num);
    }
    void show(){//重写父类方法 
        System.out.println("show num "+num);
    }
}
public class Main{
    public static void main(String[] args) {
    Son son=new Son();
    son.show();
    }
}

/*答案是  show num 0
   		 show num 8
         show num 8
*/
```

------

### final

1. final可以修饰类、方法、变量
2. final修饰类不能被继承
3. final修饰方法不能被重写
4. final修饰的变量是常量只能赋值一次

final 固定的是 显示初始化（final int x  这样尚未初始化x ，要赋值）

常量所有字母大写（规范）

