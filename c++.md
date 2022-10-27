> 2nd edition  for C++17

* 有哪些异常
* `noexcept`的函数内如果发生异常会怎么样？
* throw error要加std::吗
* cout可以输出error吗
* invarient和precondition？
* assert？
* static_assert的输出

# 01 The Basics

* Linux/Unix系统main()执行失败会返回非0值，windows很少这么做

* 函数的类型包括返回值和参数的类型序列：`double get(const vector<double>& vec,int x);`对应类型`double(const vector<double>&,int)`

* overload的同名函数需要有相同的语义

* 类型的尺寸是执行时定义的（不同机器不同），0b(base2)，0x(base16)，0(base8)

* `-x`：一元减号取负

* `~x`：按位补（每位取反）

* 表达式中不同type的数据进行计算时，保留最高精度的

* 花括号的赋值形式：花括号**不允许**损失精度/范围隐式类型转换的赋值`int x{1.9}`

  <img src="https://mdgraph-1301162508.cos.ap-shanghai.myqcloud.com/2022/20220922211103.png" style="zoom:80%;" />
  * 队列赋值：

    ```c++
    int x[4] = {1,2,3,4};
    int y[4]{1,2,3,4};
    ```

* 当不需要指定data精度/范围，以及不考虑可读性时可以使用`auto`声明数据类型

* **declare范围**

  * Local scope：声明处到block结束
  * Class scope：**整个覆盖declare的{}内**
  * Namespace scope：声明处到namespace的结尾，namespace object再程序结束时销毁

* `const`：常用于**接口中声明**，配合pointers和references，表示值在（函数）运行时不变，**运行时计算**

  * 不想要修改元素且不想要拷贝代价则使用`const+&`

* `constexpr`：表示常量，**编译时计算**，赋值时**右侧必须为常量表达式**

  * 修饰函数时，如果调用传入参数为常数则作为常数表达式（可以传入变量）；**且在函数体内不能使用非局部变量（只能使用必须加const/constexpr前缀的全局变量）**

* `for`：

  * `for(auto x:{1,2,3,4})`
  * `for(auto x:v)//int v[]{1,2,3}`对于x依次存放v的副本
  * `for(auto &x:v)`使用引用修改数组成员
  * *迭代目标不可以为指向对象的指针吗？*

* 函数传参时使用**引用**防止传入副本（节省memory），引用必须参考有效的对象

* `nullptr`：新的空指针说明（`NULL == nullptr`为），可以消除整数（`0/NULL`）和指针（`nullptr`）的歧义

* ```c++
  switch(v):
  	case 1:continue;
  	case 2:break;
  	default:printf();
  ```

* if语句也可以使用赋值加判断`if(auto n = v.size();n!=0){}`，条件中声明的变量范围在括号和if表达式中（等同于``if(auto n = v.size())`）

* 在函数体内声明引用必须初始化引用

# 02 User-Defined Types

* `new`/delete：为对象分配free store/dynamic memory/heap（“live”返回和创造范围独立，直到使用`delete`）

  ```c++
  int *a = new int[5];  //注意[]
  int *b = new int;
  
  delete[] a;
  delete b;
  ```

* class（注意**构造器**语法）

  * interface为可以公开访问的，接口实现对不可访问数据（private）的访问处理

  * function，data，type member都可以是public或者private

    ```c++
    class Vector {
    public:
    	Vector(int s) :elem{new double[s]}, sz{s} { } // constr uct a Vector！！！
    	double& operator[](int i) { return elem[i]; } 
    	int size() { return sz; }
    private:
    	double∗ elem; // pointer to the elements
    	int sz;// the number of elements
    };  //; ！！！！！！！！！
    ```

  * `struct`和`class`没有明显的区别，`struct`默认所有member都是public

* `union`：可以为多种类型，但是**同时只能选择一种**成员类型被使用（me：按对应成员类型的访问方式）

  ```c++
  union Value{
  	int a;
  	double b;
  };
  ```

  * 适用情况：互斥访问的元素，可以节省memory
  * 缺点：不可以自己判断哪个成员有效，可以使用`variant`代替

* `enum`：用于表示一个小型的可枚举整数集合

  * 默认从0开始
  * 带`class`的类型赋值时要显示带类型名称，e.g.`Color::red`

  ```c++
  enum class Color { red, blue , green };
  enum class Trafﬁc_light { green, yellow, red };
  
  Color col = Color::red;   //有混淆的value必须指明类型
  Trafﬁc_light light = Trafﬁc_light::red;
  
  enum Color { red, green, blue };
  int col = green;
  Color c = red; //不用指定类型
  ```

# 03 Modularity

# 04 Class

* 对于**内存**
  * stack上的stack释放时会执行析构函数，堆上的只能使用`delete`去执行析构函数

```c++
Class a = Class();  //只有构造函数在栈上创造对象
Class a = new Class();     //构造函数前加new，在堆上创造对象
```

* 首先要注意只有**类的成员函数**才能在函数名**后面**加上const，这时成员函数叫做**常量成员函数**。
  * 常量成员函数在执行期间不能修改成员变量的值（静态成员变量除外），也不能调用同类的非常量成员函数（同样的静态成员函数除外）
  * **const成员函数可以被const和non-const对象调用，但是non-const成员函数只能被non-object对象调用**
  * 而在函数名前加const则表示函数的返回值为常量
  
* 成员前面没有存取范围说明符的，**对class来说被认为私有成员**，对struct来说被认为公有成员

* constructor要在public内

* concrete class
  
  * `类型 object; `会自动调用无参的构造函数
  
* abstract class 
  
  > [c++ virtual 和 pure virtual的区别](https://www.cnblogs.com/qrlozte/p/4106222.html)
  
  * 一般无构造器，有deconstructor
  * 通过对派生类**指针或者引用**来使用（抽象类*v = new 派生类）
  * pure virtual
    * 加了virtual关键字，可以在Base就提供implementation，允许生成Base的objects（上述代码已验证）
    * 加了virtual关键字，并加上 **"=0"**，就成为pure virtual，Base不允许提供implementation，因此也就不允许生成Base的objects（尝试把Base.VirtualFunc改为pure的再编译，会报错，即使你提供了implementation也要报错）；希望子类**一定**要重新定义它，并且没有默认定义，必须子类自己定义
  * me：`override`和`virtual`，更像是一种对行为的声明（约束），然后编译器会去检查这种行为！
  * `override`：覆盖（重写）
  * **virtual function：**
    * 构造的时候总数使用派生类的构造器，但是销毁时可能指定基类销毁（所以要override deconstructor）（否则在delete Base-class的pointer的时候可能无法正确的执行到Sub-class的destructor），现在的编译器一般都会检测到这个问题并给出warning）
    * 析构函数**“自上而下”销毁**
  
* 对象由构造函数“**自下而上”构造**（基础优先），由析构函数**“自上而下”销毁**（派生优先）

* **`dynamic_cast`**将基类的类型**恢复**为对应派生类

  * dynamic转换的类需要加一个虚函数。任意一个虚函数都可以（me：需要证明这个可以转化的类为基类有多态性？）

  * 用法：`B* b = dynamic_cast<B*>(a);`/`B& b{dynamic_cast<B&>(*a)};`

  * 转化目标为指针，失败返回`nullptr`

  * 转化目标为**引用**，失败抛出`std::bad_cast`，不会中断程序，使用try捕获

    ```c++
    try{
    	C& c{dynamic_cast<C&>(*a)};
    }
    catch(exception& e){
        cout<<e.what();
    }
    ```

* `unique_ptr`：**智能指针**，在离开作用域后会自动`delete`
  * 创建方式

  ```python
  class Person{
      ...
  };
  # 使用unique_ptr<Class>代替 Class* 的声明
  std::unique_ptr<Person> pPerson1(new Person("P1"));
  std::unique_ptr<Person> pPerson2 = std::make_unique<Person>("P2");
  auto a = std::make_unique<Person>("Px");
  ```

  * [简单使用](https://blog.csdn.net/niaxiapia/article/details/125530820)

# other

* `inline`：

  > [C++中的inline用法 - Boblim - 博客园 (cnblogs.com)](https://www.cnblogs.com/fnlingnzb-learner/p/6423917.html)

  * 内敛函数：可以将原代码函数处直接替换（相对于`#define`可以检查参数），**为了解决**一些频繁调用的小函数大量消耗**栈空间（栈内存）**的问题
  * 只适合函数体内简单的函数，不能包含复杂的控制语句（while，switch等），不能是递归函数；只是对编译器的建议，由**编译器**决定最后是否可以内联
  * 在函数**定义处**加此关键词才有效（声明有没有关键词inline无影响），所以建议定义也在头文件中
  * 类中：**定义**在类**中**的成员函数缺省都是**内联的**。如果在类中未给出成员函数定义，而又想内联该函数的话，那在**类外要加上inline**，否则就认为不是内联的。
  * 内联是以**代码膨胀（复制）**为代价，仅仅省去了函数调用的开销，从而提高函数的执行效率。

* `volatile`：

  > [C语言中volatile关键字的作用](https://blog.csdn.net/weixin_43491077/article/details/109555669)

  * volatile提醒编译器它后面所定义的变量随时都有可能改变，因此编译后的程序每次需要存储或读取这个变量的时候，告诉编译器对该变量不做优化，**都会直接从变量内存地址中读取数据**，从而可以提供对特殊地址的稳定访问。
  * 一般用于：1、中断服务程序中修改的供其它程序检测的变量，需要加volatile；2、多任务环境下各任务间共享的标志，应该加volatile；

* `#if\#ifdef\#if defined`：用于判断其中的内容是否被**编译**

  * `#if`：宏条件中的表达式是否为true

    ```c++
    #define  A 0  //把A定义为0
    #if (A > 1)
             printf("A > 1");  //编译器没有编译该语句,该语句不生成汇编代码
    #elif (A == 1)
             printf("A == 1"); //编译器没有编译该语句,该语句不生成汇编代码
    #else
             printf("A < 1");   //编译器编译了这段代码，且生成了汇编代码，执行该语句
    #endif
    ```

  * `#if defined`：是否定义了这个宏

    ```c++
    #define A 0
    #if defined (A) // #ifdef A
        ...code...
    #endif
    ```

  * `#ifdef 宏`的使用和`#if defined(宏)`的用法一致，`#ifndef 宏`又和`#if !defined(宏)`的用法一致（**注意格式！**）

  * **最后都要`#endif`**
