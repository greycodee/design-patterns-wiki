# UML箭头的含义

## 泛化

> 在 Java 中表示继承关系，空心箭头指向父类

![image-20210717181253414](http://cdn.mjava.top/blog/fi3SUYimage-20210717181253414.png)

**示例：**

![image-20210718173428923](http://cdn.mjava.top/blog/CWFFnaimage-20210718173428923.png)

```java
class Parent {
    
}

class Son extends Parent {
    
}
```


## 实现

> 表示实现接口，箭头指向接口类

![image-20210717181304829](http://cdn.mjava.top/blog/XoAFNsimage-20210717181304829.png)

**示例：**

![image-20210718173938989](http://cdn.mjava.top/blog/OlaaSSimage-20210718173938989.png)

```java
interface Iter {

}

class TerImpl implements Iter {

}
```


## 依赖

> 表示依赖关系，某个类的方法必须依赖另一个类才可以执行，箭头指向被依赖的类

![image-20210718171936788](http://cdn.mjava.top/blog/9ULJU5image-20210718171936788.png)

**示例：**

![image-20210718174817997](http://cdn.mjava.top/blog/YEh93vimage-20210718174817997.png)

```java
class A {
    public void testA(){
        System.out.println("这是 A 类");
    }
}

class B {
    public void testB(A a){
        a.testA();
    }
}
```



## 关联关系

### 关联

> 表示关联关系，两个类的关系是平等的
>
> **可以双向关联，A 可以关联 B，B 也可以关联 A**
>
> 箭头指向被关联的类

![image-20210717181329532](http://cdn.mjava.top/blog/effJpHimage-20210717181329532.png)

**示例：**

![image-20210718201348840](http://cdn.mjava.top/blog/p17PX4image-20210718201348840.png)

```java
class A {
    public void testA(){
        System.out.println("这是 A 类");
    }
}

class B {
    private A a;

    public B(A a) {
        this.a = a;
    }

    public void testB(){
        a.testA();
    }
}
```



### 聚合

> 表示聚合关系，**聚合是关联的一种特例，在代码上两者没有什么区别**。
>
> **单向关联，A 能关联 B，B 不能关联 A**
>
> 尾部为空棱形，也可以是直线

![image-20210718195546287](http://cdn.mjava.top/blog/fKgWIFimage-20210718195546287.png)

**示例：**

![image-20210718200435303](http://cdn.mjava.top/blog/DvBzVKimage-20210718200435303.png)

```java
class A {

}

class B {
    private List<A> a;
    
}
```



### 组合

> 表示组合关系，也是**关联关系的一种**
>
> 表示强关联关系，被关联的类的生命周期会随关联类的生命周期一起产生和消失

![image-20210718195556115](http://cdn.mjava.top/blog/15FMoXimage-20210718195556115.png)

**示例：**

![image-20210718201118928](http://cdn.mjava.top/blog/1jOTPHimage-20210718201118928.png)

```java
class A {

}

class B {
    private A a;

    public B() {
        this.a = new A();
    }
}
```



## 总结

聚合和组合的区别：聚合是个体离开了整体，依然可以存在.
                                       组合是个体和整体不可以分开，个体不能离开整体单独存在。

依赖，关联 和聚合，组合的区别：依赖，关联 : 类之间的关系是在同一层次上.
                                                               聚合，组合: 类之间的关系表现为整体和部分。

### 参考资料

- https://blog.csdn.net/zhuyu714997369/article/details/51983871
- https://zhuanlan.zhihu.com/p/109655171
- https://blog.csdn.net/qq_31655965/article/details/54645220