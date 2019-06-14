# Gradle
Gradle 是一款非常优秀的构建系统工具,它的DSL基于Groovy实现,可以很方便的通过代码控制这些DSL来达到构建的目的,Gradle构建的大部分功能都是通过插件方式来实现,非常灵活方便,如果内置插件不能满足需求可以自定义插件
Gradle脚本不是像传统的xml文件那样，而是一种基于Groovy的动态DSL，而Groovy语言是一种基于jvm的动态语言。
DSL(Domain Specific Language) 中文意思是领域特定语音,就是专门关注某一领域的语言,它在于专而不是全,不像java这种通用的全面的语言.
### **Gradle Wrapper**
grade只是一个构建工具，而新版本总是在更迭，所以使用Gradle Wrapper将会是一个好的选择去避免由于gradle版本更新导致的问题。Gradle Wrapper提供了一个windows的batch文件和其他系统的shell文件，当你使用这些脚本的时候，当前gradle版本将会被下载，并且会被自动用在项目的构建，所以每个开发者在构建自己app的时候只需要使用Wrapper。所以开发者不需要为你的电脑安装任何gradle版本，在mac上你只需要运行gradlew，而在windows上你只需要运行gradlew.bat。
你也可以利用命令行./gradlew -v来查看当前gradle版本。下列是wrapper的文件夹：
   myapp/
   ├── gradlew
   ├── gradlew.bat
   └── gradle/wrapper/
       ├── gradle-wrapper.jar
       └── gradle-wrapper.properties
可以看到一个bat文件针对windows系统，一个shell脚本针对mac系统，一个jar文件，一个配置文件。配置文件包含以下信息：
#Sat May 30 17:41:49 CEST 2015
   distributionBase=GRADLE_USER_HOME
   distributionPath=wrapper/dists
   zipStoreBase=GRADLE_USER_HOME
   zipStorePath=wrapper/dists
   distributionUrl=https\://services.gradle.org/distributions/
   gradle-2.4-all.zip
你可以改变该url来改变你的gradle版本。
# Groovy
Groovy是用于Java虚拟机的一种敏捷的动态语言，它是一种成熟的面向对象编程语言，既可以用于面向对象编程，又可以用作纯粹的脚本语言。使用该种语言不必编写过多的代码，同时又具有闭包和动态语言中的其他特性。
Groovy是JVM的一个替代语言（替代是指可以用 Groovy 在Java平台上进行 Java 编程），使用方式基本与使用 Java代码的方式相同，该语言特别适合与Spring的动态语言支持一起使用，设计时充分考虑了Java集成，这使 Groovy 与 Java 代码的互操作很容易。（注意：不是指Groovy替代java，而是指Groovy和java很好的结合编程。
## 基本特点
1、构建在强大的Java语言之上 并 添加了从Python，Ruby和Smalltalk等语言中学到的 诸多特征，例如动态类型转换、闭包和元编程（metaprogramming）支持。
2、为Java开发者提供了 现代最流行的编程语言特性，而且学习成本很低。
3、支持DSL（Domain Specific Languages领域定义语言）和其它简洁的语法，让代码变得易于阅读和维护。
4、受检查类型异常(Checked Exception)也可以不用捕获。
5、Groovy拥有处理原生类型，面向对象以及一个Ant DSL，使得创建Shell Scripts变得非常简单。
6、在开发Web，GUI，数据库或控制台程序时 通过 减少框架性代码 大大提高了开发者的效率。
7、支持单元测试和模拟（对象），可以 简化测试。
8、无缝集成 所有已经存在的 Java对象和类库。
9、直接编译成Java字节码，这样可以在任何使用Java的地方 使用Groovy。
10、支持函数式编程，不需要main函数。
11、一些新的运算符。
12、默认导入常用的包。
13、断言不支持jvm的-ea参数进行开关。
14、支持对对象进行布尔求值。
15、类不支持default作用域，且默认作用域为public。
16、groovy中基本类型也是对象，可以直接调用对象的方法。

## 动态类型
类型对于变量，属性，方法，闭包的参数以及方法的返回类型都是可有可无的，都是在给变量赋值的时候才决定它的类型， 不同的类型会在后面用到，任何类型都可以被使用,即使是基本类型 (通过自动包装（autoboxing）). 当需要时，很多类型之间的转换都会自动发生，比如在这些类型之间的转换: 字符串（String），基本类型(如int) 和类型的包装类 (如Integer)之间，可以把不同的基本类型添加到同一数组（collections）中。
## 闭包
闭包就是可以使用参数的代码片段，每个闭包会被编译成继承groovy.lang.Closure类的类，这个类有一个叫call方法，通过该方法可以传递参数并调用这个闭包.它们可以访问并修改在闭包创建的范围内的变量，在闭包内创建的变量在闭包被调用的范围内同样可以被引用， 闭包可以保存在变量中并被作为参数传递到方法中。
## 语法
Groovy 语法与Java 语言的语法很相似，虽然 Groovy 的语法源于Smalltalk和Ruby这类语言的理念，但是可以将它想像成 Java 语言的一种更加简单、表达能力更强的变体。（在这点上，Ruby与 Groovy 不同，因为它的语法与 Java 语法差异很大。）
许多 Java 开发人员喜欢 Groovy 代码和 Java 代码的相似性。从学习的角度看，如果知道如何编写 Java 代码，那就已经了解 Groovy 了。Groovy 和 Java 语言的主要区别是：完成同样的任务所需的 Groovy 代码比 Java 代码更少。
## 类

Groovy类和java类一样，完全可以用标准java bean的语法定义一个Groovy类。但作为另一种语言，可以使用更Groovy的方式定义类，这样的好处是，可以少写一半以上的javabean代码。

与Java区别
（1）不需public修饰符
如前面所言，Groovy的默认访问修饰符就是public，如果Groovy类成员需要public修饰，则根本不用写它。
（2）不需要类型说明
同样前面也说过，Groovy也不关心变量和方法参数的具体类型。
（3）不需要getter/setter方法
在很多ide（如eclipse）早就可以为程序员自动产生getter/setter方法了，在Groovy中，不需要getter/setter方法--所有类成员（如果是默认的public）根本不用通过getter/setter方法引用它们（当然，如果一定要通过getter/setter方法访问成员属性，Groovy也提供了它们）。
（4）不需要构造函数
不再需要程序员声明任何构造函数，因为实际上只需要两个构造函数（1个不带参数的默认构造函数，1个只带一个map参数的构造函数--由于是map类型，通过这个参数可以构造对象时任意初始化它的成员变量）。
（5）不需要return
Groovy中，方法不需要return来返回值。
（6）不需要（）
# 教程 
 [https://www.w3cschool.cn/groovy/groovy_basic_syntax.html](https://www.w3cschool.cn/groovy/groovy_basic_syntax.html)

### **Project和tasks**
在grade中的两大重要的概念，分别是project和tasks。每一次构建都是有至少一个project来完成，。每个project有至少一个tasks。每一个build.grade文件代表着一个project。tasks在build.gradle中定义。当初始化构建进程，gradle会基于build文件，集合所有的project和tasks,一个tasks包含了一系列动作，然后它们将会按照顺序执行，一个动作就是一段被执行的代码，很像Java中的方法。编译过程分为三个阶段：

1.初始化阶段中，Gradle决定哪些项目加入到构建中（因为Gradle支持多项目构建），并为这些项目分别创建一个Project实例。
Gradle在初始化阶段会首先去查找setting.gradle文件
查找当前构建目录下的setting.gradle文件。
Gradle去检查当前项目在settings.gradle中是否有定义。如果没有，则进行单项目构建，否则进行多项目构建。

2.配置阶段：在该阶段，build.gradle脚本将会执行，为每个project创建和配置所有的tasks。

3.执行阶段，首先，Gradle确定要执行的任务集，任务集是由输入到命令行的任务名称参数和当前目录决定的。然后，Gradle会去执行任务集中的每个任务。
 任务（Task）是由一系列的活动（Action）组成的，当任务执行的时候，活动会依次执行。可以通过doFirst和doLast方法将活动添加到任务中。

 
### **build.gradle的配置文件**
基于grade构建的项目通常至少有一个build.gradle，那么我们来看看Android的build.gradle：
buildscript {
   repositories {
        jcenter()
   }
   dependencies {
       classpath 'com.android.tools.build:gradle:1.2.3'
 **}** 
}
这个就是实际构建开始的地方，在仓库地址中，我们使用了JCenter，JCenter类似maven库，不需要任何额外的配置，grade还支持其他几个仓库，不论是远程还是本地仓库。
构建脚本也定义了一个Android构建工具，这个就是Android plugin的来源之处。

Android plugin提供了所有需要去构建和测试的应用。每个Android应用都需要这么一个插件：
apply plugin: 'com.android.application'
插件用于扩展gradle脚本的能力，在一个项目中使用插件，这样该项目的构建脚本就可以定义该插件定义好的属性和使用它的tasks。打包 编译 运行



### **使用基本的构建命令**
使用你的命令行，导航到你的项目，然后输入：
**$** gradlew tasks
这一命令将会列出所以可运行的tasks,你也可以添加--all参数，来查看所有的task。
当你在开发的时候，构建项目，你需要运行assemble task通过debug配置：
**$** gradlew assembleDebug
该任务将会创建一个debug版本的app,同时Android插件会将其保存在MyApp/app/build/ outputs/apk目录下。
除了assemble，还有三个基本的命令：
* check 运行所以的checks,这意味着运行所有的tests在已连的设备或模拟器上。
* build 是check和assemble的集合体。
* clean 清楚项目的output文件。
# 打包流程梳理
# ![图片](https://uploader.shimo.im/f/QnsquibuBfI6p8L6.png!thumbnail)
我们可以将整个打包过程概括为以下几步：
1. 通过aapt打包res资源文件，生成R.java、resources.arsc和res文件（二进制 & 非二进制如res/raw和pic保持原样）
2. 处理.aidl文件，生成对应的Java接口文件
3. 通过Java Compiler编译R.java、Java接口文件、Java源文件，生成.class文件
4. 通过dex命令，将.class文件和第三方库中的.class文件处理生成classes.dex
5. 通过apkbuilder工具，将aapt生成的resources.arsc和res文件、assets文件和classes.dex一起打包生成apk
6. 通过Jarsigner工具，对上面的apk进行debug或release签名
7. 通过zipalign工具，将签名后的apk进行对齐处理。
# ![图片](https://uploader.shimo.im/f/G7ZxUmYUoVcEDzie.png!thumbnail)
# ![图片](https://uploader.shimo.im/f/KmHyDlQRQU8ckR7y.png!thumbnail)
![图片](https://uploader.shimo.im/f/X0x8BG8WwsQOLxIQ.png!thumbnail)


# gradle 教程
[https://www.w3cschool.cn/gradle/6qo51htq.html](https://www.w3cschool.cn/gradle/6qo51htq.html)
# 闭包的理解
 
闭包（Closure）是很多编程语言中很重要的概念，那么Groovy中闭包是什么，官方定义是“**Groovy中的闭包是一个开放，匿名的代码块，可以接受参数，返回值并分配给变量**”，简而言之，他说一个匿名的代码块，可以接受参数，有返回值，那么到底是怎么样的，我们来探究一下：
 
## - 如何定义
 
> 
>定义闭的语意 ：{ [closureParameters -> ] statements }
> 

 
其中[closureParameters->]代表参数们，多参数用逗号分割，用->隔开参数与内容，没有参数可以不写->
 
### - 闭包的写法
![图片](https://uploader.shimo.im/f/YXiLWUgDefUjqfcU.png!thumbnail) 
### - groovy.lang.Closure对象
 
其实，每定义的闭包是一个Closure对象，我们可以把一个闭包赋值给一个变量
 
![图片](https://uploader.shimo.im/f/2zs3lwGZPeYqbqtW.png!thumbnail)

 
 
如何执行闭包对象呢，执行闭包对象有两种，一是直接用括号+参数，二是调用call方法
 ![图片](https://uploader.shimo.im/f/YCHYfWW25MYj4PRQ.png!thumbnail) 
### - 理解闭包内this，owner，delegate对象
在闭包内部，有三个内置对象this，owner，delegate，我们可以直接this，owner，delegate调用，或者用get方法：
  
* getThisObject()  等于 this
* getOwner()  等于 owner
* getDelegate() 等于delegate 

那么这三个对象，分别指代的是哪个对象，是否和java的this关键字一样，我们先做文字解释：
 
*  **this**   对应于定义闭包的那个类，如果在内部类中定义，指向的是内部类
*  **owenr**  对应于定义闭包的那个类或者闭包，如果在闭包中定义，对应闭包，否则同this一致 

 **delegate**  默认是和owner一致，或者自定义delegate指向
*  我们来用代码验证一下

 ![图片](https://uploader.shimo.im/f/L3BxZnvBRwkqXtPS.png!thumbnail)


 
我们在OuterClass定义一个内部类InnerClass，在InnerClass中定义了一个outerClosure闭包，在outerClosure中定义了一个innerClosure闭包，现在我们分别打印innerClosure和outerClosure闭包对应的this，owner，delegate对象和outerClosure对象的toString方法
 ![图片](https://uploader.shimo.im/f/ObLc0Qs3UWsccbJ9.png!thumbnail)
 
分析结果：
 
* **innerClosure**
* this：结果是OuterClass$InnerClass对象
* owner：结果是OuterClass$InnerClass$_closure1对象 ，即outerClosure
* delegate：同owenr 
* **outerClosure **
* this：结果是OuterClass$InnerClass对象
* owner：结果是OuterClass$InnerClass对象
* delegate：同owenr

this，owner ，delegate指向总结：
 **this** 永远是指定义该闭包类，如果存在内部类，则是最内层的类，但this不是指当前闭包对象
 **owenr** 永远是指定义该闭包的类或者闭包，顾名思义，闭包只能定义在类中或者闭包中
 ** delegate** 默认是指owner，可以自己设置，自己设置的话又是什么情况
 
### - delegate才是重头戏
 
前面已经说了，闭包可以设置delegate对象，**设置delegate的意义就是讲闭包和一个具体的对象关联起来**，这个如何理解，看代码：
 
![图片](https://uploader.shimo.im/f/xuSAY4zUHJkOvh1R.png!thumbnail)
我们定义Person实体类，再定义一个名字叫cc的闭包，我们想在闭包里修改Person的name和age，还想调用eat方法，这个怎么关联起来？
 
![图片](https://uploader.shimo.im/f/NfH7QNE8TrAV3Au7.png!thumbnail)

 
![图片](https://uploader.shimo.im/f/dLu5dzyeGqIx5fmU.png!thumbnail)


上面我们知道了，在闭包中可以访问被代理对象的属性和方法，哦，那么我还有一个疑问，如果闭包所在的类或闭包中和被代理的类中有相同名称的方法，到底要调用哪个方法，其实这个问题groovy肯定考虑到了，为我们设定了几个代理的策略：
* Closure.OWNER_FIRST是默认策略。优先在owner寻找，owner没有再delegate
* Closure.DELEGATE_FIRST：优先在delegate寻找，delegate没有再owner
* Closure.OWNER_ONLY：只在owner中寻找
* Closure.DELEGATE_ONLY：只在delegate中寻找 

# Android Gradle
[https://www.jianshu.com/p/8e89a0b8acf8](https://www.jianshu.com/p/8e89a0b8acf8)
# 自定义插件
# 1 自定义Android Gradle插件
[https://blog.csdn.net/binbinqq86/article/details/81033746](https://blog.csdn.net/binbinqq86/article/details/81033746)

讲解 360 打包加固demo
# 2 自定义Studio插件
[https://blog.csdn.net/csdn_xpw/article/details/78946781](https://blog.csdn.net/csdn_xpw/article/details/78946781)
[https://blog.csdn.net/ExcellentYuXiao/article/details/80273347](https://blog.csdn.net/ExcellentYuXiao/article/details/80273347)
[https://blog.csdn.net/ExcellentYuXiao/article/details/80273448](https://blog.csdn.net/ExcellentYuXiao/article/details/80273448)

[https://cloud.tencent.com/developer/article/1348741](https://cloud.tencent.com/developer/article/1348741)

![图片](https://uploader.shimo.im/f/Uoo5E2KpYyACO6NT.png!thumbnail)
![图片](https://uploader.shimo.im/f/gF5MWo5Fiq8DfGu4.png!thumbnail)

demo
![图片](https://uploader.shimo.im/f/VUHuHpYh9TQCHHCb.png!thumbnail)
![图片](https://uploader.shimo.im/f/ODBlfgySK8MYXkr1.png!thumbnail)

![图片](https://uploader.shimo.im/f/K3Y1YgevGlQDJY3W.png!thumbnail)

![图片](https://uploader.shimo.im/f/aYd2cSltooQh8Q19.png!thumbnail)
![图片](https://uploader.shimo.im/f/IQ3KE72VW9o7cbRY.png!thumbnail)

IDEA插件开发工具SDK文档
[http://www.jetbrains.org/intellij/sdk/docs/basics/architectural_overview/psi_files.html](http://www.jetbrains.org/intellij/sdk/docs/basics/architectural_overview/psi_files.html)

[https://blog.csdn.net/w855227/article/details/79483966](https://blog.csdn.net/w855227/article/details/79483966)
