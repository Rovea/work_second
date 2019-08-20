# Why should you have minimum scope for variables?

变量主要包括成员变量和局部变量，局部变量相对成员变量作用范围小；成员变量随着对象的建立而建立，随着对象的消失而消失，存在于对象所在的堆内存中，
成员变量有默认初始化值。局部变量只定义在局部范围内，存在于栈内存中，作用的范围结束，变量空间会自动释放，并且局部变量没有默认初始化值；所以作
用范围越小，更能节约内存，并且不会收到其它方法的干扰。

# Why should you understand performance of String Concatenation?

拼接字符串的方法有“+”、StringBuffer、StringBuilder和String.concat()，当拼接数量很多时，“+”会消耗很大的内存和时间，所以这种情况下一般选择StringBuffe
或StringBuilder。concat()方法使用了StringBuilder，concat()的性能应该和StringBuilder的一样好，但是由于额外的创建StringBuilder和做
.append(str).append(str).toString()的操作，使得concate的性能会受到一些影响。

# What are the best practices with Exception Handling?

1、为可恢复的错误使用检查型异常，为编程错误使用非检查型错误。
2、在finally程序块中关闭或者释放资源
3、在堆栈跟踪中包含引起异常的原因
4、始终提供关于异常的有意义的完整的信息
5、避免过度使用检查型异常
6、将检查型异常转为运行时异常
7、对性能而言，异常代价高昂
8、避免catch块为空
9、使用标准异常
10、记录任何方法抛出的异常

# When is it recommended to prefer Unchecked Exceptions?
在调用者可能能够以某种有效的方式恢复的情况下，会调用一个检查过的异常，而对于无法恢复的情况，作为一个未检查的异常。

# When do you use a Marker Interface?

标识接口是没有任何方法和属性的接口。标识接口不对实现它的类有任何语义上的要求，它仅仅表明实现它的类属于一个特定的类型。它们的存在是为了允许使用实现它的
对象的代码检查它们是否实现了所述接口，如果有，则以不同的方式处理对象。

# Why are ENUMS important for Readable Code?

能够更加明确的表明一些状态码或者其它数据、同时避免一些输入错误。

# Why should you minimize mutability?

1、可以保证数据的安全；
2、在使用的时候更加方便；
3、线程安全。

# What is functional programming?

不依赖外部数据，每一个方法或函数都是单独的个体，不会改变外部的任何值，而是返回一个新的值。
三大特性：
1、不可变数据
2、first class functions
3、尾递归优化

# Why should you prefer Builder Pattern to build complex objects? 

通过构造器，生成对象，然后根据set方法来给对象赋值。 容易造成线程不安全，对象处于不一致状态。类无法仅仅通过检验构造器参数的有效性来保证一致性。
而调用构造器生成 build 对象，然后在 build 对象上类似 set 方法来设置每个相关的可选参数；最后调用 build() 方法生成不可变的对象。

# should you avoid floats for Calculations?

浮点类型运算精度不准。

# Why should you build the riskiest high priority features first?

