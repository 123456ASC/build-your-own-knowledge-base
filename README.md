## 使用docsify搭建自己的知识库



#### 本地安装 nodejs，然后执行安装 docsify 命令

```
npm install -g docsify-cli
docsify -v
```

新建一个目录

docsify init

然后输入  **y**

```
 docsify serve
```

访问： http://localhost:3000，看到这个页面















axios  从入门到源码分析




![image-20240315091340321](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20240315091340321.png)

二级缓存





![image-20240312193523313](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20240312193523313.png)

Stream流的中间方法



![image-20240301134420651](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20240301134420651.png)

Stream流的终结方法



![image-20240301134258676](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20240301134258676.png)

![image-20240301141009140](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20240301141009140.png)





Socket数据传输


![image-20240227104357439](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20240227104357439.png)





文件传输



https://gimg3.baidu.com/search/src=https%3A%2F%2Fstatic-data.gaokao.cn%2Fupload%2Flogo%2F140.jpg%3Ft%3D1686548544&refer=http%3A%2F%2Fwww.baidu.com&app=2021&size=w931&n=0&g=0n&er=404&q=75&fmt=auto&maxorilen2heic=2000000?sec=1709139600&t=1fd2dbc1d7bed1ba011248b736c935a1



![](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20240228154502698.png)













## 2023.12.3反射

package fanshe;

public class Student {
	

	//---------------构造方法-------------------
	//（默认的构造方法）
	Student(String str){
		System.out.println("(默认)的构造方法 s = " + str);
	}
	
	//无参构造方法
	public Student(){
		System.out.println("调用了公有、无参构造方法执行了。。。");
	}
	
	//有一个参数的构造方法
	public Student(char name){
		System.out.println("姓名：" + name);
	}
	
	//有多个参数的构造方法
	public Student(String name ,int age){
		System.out.println("姓名："+name+"年龄："+ age);//这的执行效率有问题，以后解决。
	}
	
	//受保护的构造方法
	protected Student(boolean n){
		System.out.println("受保护的构造方法 n = " + n);
	}
	
	//私有构造方法
	private Student(int age){
		System.out.println("私有的构造方法   年龄："+ age);
	}

}

```
/**
 * 获取Class对象的三种方式
 * 1 Object ——> getClass();
 * 2 任何数据类型（包括基本数据类型）都有一个“静态”的class属性
 * 3 通过Class类的静态方法：forName（String  className）(常用)
 *
 */
public class Fanshe {
   public static void main(String[] args) {
      //第一种方式获取Class对象  
      Student stu1 = new Student();//这一new 产生一个Student对象，一个Class对象。
      Class stuClass = stu1.getClass();//获取Class对象
      System.out.println(stuClass.getName());
      
      //第二种方式获取Class对象
      Class stuClass2 = Student.class;
      System.out.println(stuClass == stuClass2);//判断第一种方式获取的Class对象和第二种方式获取的是否是同一个
      
      //第三种方式获取Class对象
      try {
         Class stuClass3 = Class.forName("Student");//注意此字符串必须是真实路径，就是带包名的类路径，包名.类名
         System.out.println(stuClass3 == stuClass2);//判断三种方式是否获取的是同一个Class对象
      } catch (ClassNotFoundException e) {
         e.printStackTrace();
      }
      
   }
}
```



![image-20231203204306600](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231203204306600.png)

## 微服务

![image-20231203140514136](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231203140514136.png)

![image-20231203140533887](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231203140533887.png)微服务与SpringCloud的关系

SpringCloud简单来说是上述微服务架构技术落地实现的集合体，是微服务架构下的一站式解决方案。
SpringCloud是一个技术的集合体，将上述的微服务架构进行落地。下面看一下这个集合体里包含哪些组件：
**注册中心Eureka:**
拆分成多个服务之后，总得有个管理多个服务的模块吧，这就是注册中心的作用。起到服务注册和服务发现的作用。
**网关Zuul:**
拆分成多个服务之后，涉及到服务之间的调用吧，一个服务调用了三个服务的模块，那在这个服务里，配置三个调用地址，看起来是不是很麻烦呀，所以就出现了网关，所有的服务调用都调用到网关，然后在网关里配置路由，进行服务的转发，类似于代理的作用。当然网关需要配合注册中心进行使用，去发现转发到哪个服务上去。
**负载均衡Ribbon:**
网关找到请求发送到哪个服务后，如果这个服务做了集群，有多个实例，那该发送到哪个实例上呢，于是就出现了Ribbon组件，进行负载均衡。
**远程调用方式Feign:**
服务之间相互调用的时候，可以使用RestTemplate进行调用，SpringCloud也提供了Feign客户端访问，即提供了一种远程调用方式。
**断路器Hystrix:**
SpringCloud提供了一个监控组件，用于监控服务接口的状态和断路情况。Hystrix Dashboard是个监控面板，提供了可视化界面查看服务调用的耗时等等。

2023.12.2

Eureka



# 哈希算法

哈希也称“散列”函数或“杂凑”函数。它是一个不可逆的单向映射，将任意长度的输入消息M（或文件F）映射成为一个较短的定长哈希值H（M），也叫散列值（HashValue）、杂凑值或消息摘要。可见，这是一种单向密码体制，只有加密过程，没有解密过程（因此[Hash](https://so.csdn.net/so/search?q=Hash&spm=1001.2101.3001.7020)求逆很困难）。

哈希的原理和特点

```
单向性：从哈希值不能反向推导原始数据（计算不可行），即从哈希输出无法倒推输入的原始数值。这是哈希函数安全性的基础。
灵敏性：对输入数据敏感，哪怕只改了一个Bit，得到的哈希值也大不相同。换言之，消息M的任何改变都会导致哈希值H（M）发生改变。
易压易算：Hash本质上是把一个大范围集合映射到另一个小范围集合。故输入值的个数必须与小范围相当或者更小，不然冲突就会很多。所以，哈希算法执行效率要高，散列结果要尽量均衡。
抗碰撞性：理想Hash函数是无碰撞的，但实际上很难做到这一点。有两种抗碰撞性：一种是弱抗碰撞性，即对于给定的消息，要发现另一个消息，满足在计算上是不可行的；另一种是强抗碰撞性，即对于任意一对不同的消息，使得在计算上也是不可行的。
```

也可以这么理解：正向快速、逆向困难、输入敏感、冲突避免



三、哈希的实际用途

Hash能把一个大范围映射到一个小范围，能对输入数据或文件进行校验，还可用于查找等。具体的：

```
唯一标识或数据检验：能够对输入数据或文件进行校验，判断是否相同或是否被修改。如图片识别，可针对图像二进制流进行摘要后MD5，得到的哈希值作为图片唯一标识；如文件识别，服务器在接受文件上传时，对比两次传送文件的哈希值，若相同则无须再次上传（传统的奇偶校验和CRC校验一定程度上能检测并纠正数据传输中的信道误码，但没有抗数据篡改的能力）。
安全加密：对于敏感数据比如密码字段进行MD5或SHA加密传输。哈希算法还可以检验信息的拥有者是否真实。如，用保存密码的哈希值代替保存密码，基本可以杜绝泄密风险。
数字签名。由于非对称算法的运算速度较慢，所以在数字签名协议中，单向散列函数扮演了一个重要的角色。对Hash值，又称“数字摘要”进行数字签名，在统计上可以认为与对文件本身进行数字签名是等效的。
散列函数:是构造散列表的关键。它直接决定了散列冲突的概率和散列表的性质。不过相对哈希算法的其他方面应用，散列函数对散列冲突要求较低，出现冲突时可以通过开放寻址法或链表法解决冲突。对散列值是否能够反向解密要求也不高。反而更加关注的是散列的均匀性，即是否散列值均匀落入槽中以及散列函数执行的快慢也会影响散列表性能。所以散列函数一般比较简单，追求均匀和高效。
*负载均衡：常用的负载均衡算法有很多，比如轮询、随机、加权轮询。如何实现一个会话粘滞的负载均衡算法呢？可以通过哈希算法，对客户端IP地址或会话SessionID计算哈希值，将取得的哈希值与服务器列表大小进行取模运算，最终得到应该被路由到的服务器编号。这样就可以把同一IP的客户端请求发到同一个后端服务器上。
*数据分片：比如统计1T的日志文件中“搜索关键词”出现次数该如何解决？我们可以先对日志进行分片，然后采用多机处理，来提高处理速度。从搜索的日志中依次读取搜索关键词，并通过哈希函数计算哈希值，然后再跟n(机器数)取模，最终得到的值就是应该被分到的机器编号。这样相同哈希值的关键词就被分到同一台机器进行处理。每台机器分别计算关键词出现的次数，再进行合并就是最终结果。这也是MapReduce的基本思想。再比如图片识别应用中给每个图片的摘要信息取唯一标识然后构建散列表，如果图库中有大量图片，单机的hash表会过大，超过单机内存容量。这时也可以使用分片思想，准备n台机器，每台机器负责散列表的一部分数据。每次从图库取一个图片，计算唯一标识，然后与机器个数n求余取模，得到的值就是被分配到的机器编号，然后将这个唯一标识和图片路径发往对应机器构建散列表。当进行图片查找时，使用相同的哈希函数对图片摘要信息取唯一标识并对n求余取模操作后，得到的值k，就是当前图片所存储的机器编号，在该机器的散列表中查找该图片即可。实际上海量数据的处理问题，都可以借助这种数据分片思想，突破单机内存、CPU等资源限制。
```


[springboot版本](https://so.csdn.net/so/search?q=springboot版本&spm=1001.2101.3001.7020)的问题 springboot3.0 需要jdk17支持，如果没有安装jdk17 只需把springboot版本降低即可

![image-20231011233725959](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231011233725959.png)

### sql 批量添加

DELETE FROM user WHERE 1;

INSERT INTO user (id, name, age, email) VALUES
(1, 'Jone', 18, 'test1@baomidou.com'),
(2 'Jack', 20, 'test2@baomidou.com'),
(3, 'Tom', 28, 'test3@baomidou.com',
(4, 'Sandy', 21, 'test4@baomidou.com'),
(5, 'Billie', 24, 'test5@baomidou.com');

![image-20231012001753845](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231012001753845.png)

```
# DataSource Config
spring:
  datasource:
    username: root
    password: 123456
    url: jdbc:mysql:///mybatis_plus?userUnicode=true&characterEncoding=utf-8
    driver-class-name: com.mysql.cj.jdbc.Driver
# 配置日志
mybatis-plus:
  configuration:
    log-impl: org.apache.ibatis.logging.stdout.StdOutImpl
```

### 用[雪花算法](https://so.csdn.net/so/search?q=雪花算法&spm=1001.2101.3001.7020)+UUID(不含中划线) 		

 * ```
   `/**`
   ```

  * `生成ID类型枚举类`
    `*`

    * `@author hubin`

    * `@since 2015-11-10`
      `*/`
      `@Getter`
      `public enum IdType {`
      `/**`

       * `数据库ID自增`

       * <p>该类型请确保数据库设置了 ID自增 否则无效</p>

      `*/`
         `AUTO(0),`
         `/**`

       * `该类型为未设置主键类型(注解里等于跟随全局,全局里约等于 INPUT)`
         `*/`
         `NONE(1),`
         `/**`

       * `用户输入ID`

       * <p>该类型可以通过自己注册自动填充插件进行填充</p>

         `*/`
          `INPUT(2),`

       

       

       

       

       

       

       

       

       

       

       

       

       

        

    `/* 以下3种类型、只有当插入对象ID 为空，才自动填充。 */`
       `/**`

        * `分配ID (主键类型为number或string）,`

     * `默认实现类 {@link com.baomidou.mybatisplus.core.incrementer.DefaultIdentifierGenerator}(雪花算法)`
       `*`
     * `@since 3.3.0`
       `*/`
       `ASSIGN_ID(3),`
       `/**`
     * `分配UUID (主键类型为 string)`
     * `默认实现类 {@link com.baomidou.mybatisplus.core.incrementer.DefaultIdentifierGenerator}(UUID.replace("-",""))`
       `*/`
       `ASSIGN_UUID(4);`

    `private final int key;`

    `IdType(int key) {`
        `this.key = key;`
    `}`
    `}`   

```
 
 ### UUID
 
 UUID(Universally Unique Identifier)的标准型式包含32个16进制数字，以连字号分为五段，形式为8-4-4-4-12的36个字符，示例：550e8400-e29b-41d4-a716-446655440000，到目前为止业界一共有5种方式生成UUID，详情见IETF发布的UUID规范 A Universally Unique IDentifier (UUID) URN Namespace。优点：
 
     性能非常高：本地生成，没有网络消耗。
 
 缺点：
 
     没有排序，无法保证趋势递增。
     
     UUID往往使用字符串存储，查询的效率比较低。
     
     不易于存储：UUID太长，16字节128位，通常以36长度的字符串表示，很多场景不适用。
     
     信息不安全：基于MAC地址生成UUID的算法可能会造成MAC地址泄露，这个漏洞曾被用于寻找梅丽莎病毒的制作者位置。
     
     ID作为主键时在特定的环境会存在一些问题，比如做DB主键的场景下，UUID就非常不适用：
     
         MySQL官方有明确的建议主键要尽量越短越好[4]，36个字符长度的UUID不符合要求。
     
         对MySQL索引不利：如果作为数据库主键，在InnoDB引擎下，UUID的无序性可能会引起数据位置频繁变动，严重影响性能。
 #### SnowFlake（雪花算法）

## 自动填充

### 5.1、什么是自动填充

在常用业务中有些属性需要配置一些默认值，MyBatis-Plus提供了实现此功能的插件,也就是自动填充功能。比如创建时间、修改时间这些操作一般都是自动化完成的，是不用去手动更新的。

![image-20231012003246340](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231012003246340.png)
```

# 迭代器	

**迭代器（iterable）是一个超级接口！** 是可以[遍历集合](https://so.csdn.net/so/search?q=遍历集合&spm=1001.2101.3001.7020)的对象，为各种容器提供了公共的操作接口，隔离对容器的遍历操作和底层实现，从而解耦。

![image-20231012162653556](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231012162653556.png)

> 1.API -> 只有一个方法 iterator() - 获取一个迭代器
>
> 2.迭代器:
> 	a.作用:遍历/迭代集合(数组)所有元素
> 	b.三个方法:
> 		hashNext() - 询问有没有下一个元素
> 		next() - 移动到下一个元素,并返回该位置上的元素
> 		remove() - 删除集合元素

### **什么是迭代器？**

> 先说说它是干嘛的吧！迭代器的作用是用来访问容器（用来保存元素的数据结构）中的元素，所以使用迭代器，我们就可以访问容器中里面的元素。没错！这和访问数组这个序列的指针一样，因为数组范围内的指针就是迭代器的一种。

![image-20231012191843431](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231012191843431.png)

# Lambda 表达式























# Java中List的详细用法

定义：List name = new [ArrayList](https://so.csdn.net/so/search?q=ArrayList&spm=1001.2101.3001.7020)<>()

### 1.list中添加，获取，删除元素；

添加方法是：.add(e)；　　获取方法是：.get(index)；　　删除方法是：.remove(index)； 按照索引删除；　　.remove(Object o)； 按照元素内容删除；

List<String> person = new ArrayList<>();
		person.add("jackie");
		person.add("peter");
		person.add("annie");
		person.add("martin");
		person.add("marry");
		

```
	person.remove(3);
	person.remove("marry");
	
	String per="";
	per = person.get(1);
	System.out.println("per:"+per);
	System.out.print("result:");
	for(String pers : person)
	{
		System.out.print("\t"+pers);
	}
```

### 2.list中是否包含某个元素；

方法：.contains（Object o）； 返回true或者false

、List<String> fruits = new ArrayList<>();
		fruits.add("苹果");
		fruits.add("香蕉");
		fruits.add("桃子");
		System.out.println("fruits中包含水果:");
		for(int i=0;i<fruits.size();i++)
		{
			System.out.println(fruits.get(i));
		}
		

```
	String appleString = "苹果";
	System.out.printf("fruits中%s苹果\n",fruits.contains(appleString)?"包含":"不包含");
	
	if(fruits.contains(appleString))
		System.out.println("我喜欢吃苹果");
	else
		System.out.println("我不喜欢吃苹果");
```

# 算法之暴力破解法（穷举法)

暴力破解法，就是把所有条件，相关情况统统考虑进去，让计算机进行检索，指导得出与之所有条件符合的结果

public static boolean areArraysElementsEqualUnordered(String[] array1, String[] array2) {
    // 如果任一数组为null，返回false
    if (array1 == null || array2 == null) {
        return false;
    }

```
// 遍历第一个数组的每个元素
for (String element : array1) {
    Boolean found = null;

    // 在第二个数组中查找当前元素
    for (String element2 : array2) {
        // 如果找到相同的元素，将found标记为true并跳出内层循环
        if (element.equals(element2)) {
            found = true;
            break;
        }
    }

    // 如果在第二个数组中未找到当前元素，返回false
    if (Objects.isNull(found)) {
        return false;
    }
}

// 如果成功遍历第一个数组的所有元素，则返回true
return true;
```

}

````
这段代码使用了 `Collections.sort` 方法对 `quList` 集合进行排序，排序的规则由 `PaperSort` 类的实例决定。以下是对这段代码的解释：

```
javaCopy codePaperSort paperSort = new PaperSort();
Collections.sort(quList, paperSort);
```

解释：

1. `PaperSort` 类是一个实现了 `Comparator` 接口的类，它定义了用于排序的比较规则。
2. 通过 `new PaperSort()` 创建了 `PaperSort` 类的一个实例 `paperSort`。
3. `Collections.sort` 方法用于对集合进行排序。在这里，`quList` 是待排序的集合，而 `paperSort` 是用于比较元素的排序规则。
4. 当调用 `Collections.sort(quList, paperSort)` 时，它将使用 `paperSort` 中定义的比较规则对 `quList` 进行排序。

总体而言，这段代码的目的是对 `quList` 进行排序，排序规则由 `PaperSort` 类中的比较方法决定。这是一种定制排序的方式，允许你根据特定的需求定义排序逻辑。
````

# MyBatis 动态SQL之＜foreach＞标签

# MybatisPlus条件查询与分页查询

```
<select id="queryClassIdOrTeacherIdOrCourseId" resultType="com.computertest.pojo.po.ElTeach">
    SELECT * FROM el_teach
    <where>
        <if test="classId != null and classId != ''">
            AND class_id    = #{classId}
        </if>
        <if test="teacherId != null and teacherId != ''">
            AND teacher_id = #{teacherId}
        </if>    
        <if test="courseId != null and courseId != ''">
            AND course_id = #{courseId}
        </if>
    </where>
    LIMIT #{page}, #{size}
</select>
```

# mybatis 使用FIND_IN_SET	

# 线程与进程

进程是一个具有一定独立功能的程序在一个数据集合上依次动态执行的**过程**。进程是一个正在执行的程序的实例，包括程序计数器、寄存器和程序变量的当前值。

# Mp

[MyBatis-Plus](https://github.com/baomidou/mybatis-plus)[ ](https://github.com/baomidou/mybatis-plus)[ (opens new window)](https://github.com/baomidou/mybatis-plus)（简称 MP）是一个 [MyBatis](https://www.mybatis.org/mybatis-3/)[ ](https://www.mybatis.org/mybatis-3/)[ (opens new window)](https://www.mybatis.org/mybatis-3/) 的增强工具，在 MyBatis 的基础上只做增强不做改变，为简化开发、提高效率而生。

![image-20231015172459692](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015172459692.png)

## [@TableName](https://github.com/baomidou/mybatis-plus/blob/3.0/mybatis-plus-annotation/src/main/java/com/baomidou/mybatisplus/annotation/TableName.java)

## 描述：表名注解，标识实体类对应的表

- 使用位置：实体类

## [@TableId]

- 描述：主键注解
- 使用位置：实体类主键字段

![image-20231015171342726](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015171342726.png)

![image-20231015171358806](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015171358806.png)

![image-20231015171412189](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015171412189.png)

![image-20231015172540213](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015172540213.png)

![image-20231015172558984](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015172558984.png)

![image-20231015172630496](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015172630496.png)

## crud

![image-20231015173952136](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015173952136.png)

![image-20231015174031352](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015174031352.png)

![image-20231015174052162](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015174052162.png)

![image-20231015174254711](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015174254711.png)

![image-20231015174306151](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015174306151.png)

![image-20231015174318591](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015174318591.png)

![image-20231015174330392](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015174330392.png)

![image-20231015174349794](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015174349794.png)

![image-20231015174504498](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015174504498.png)

> ![关闭端口](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231015212354403.png)

netstat -nao | findstr 8181

taskkill /f /t /im 7940

```
  int count = (int) count(new QueryWrapper<QuType>().eq("name",type.getName()));
if (count>0){
    return ResultUtils.error("该题型已存在");
}
```

```
    QueryWrapper<QuType> quTypeQueryWrapper = new QueryWrapper<>();
        Long count = quTypeMapper.selectCount(quTypeQueryWrapper.eq("name", type.getName()));
        System.out.println(count);
if (count>0){
    return new Result(20000,"sljd","fja",count);
}
        quTypeMapper.insert(type);
        return new Result(MddipEnum.SUCCESS_MESSAGE_CODE.getCode(), MddipEnum.SUCCESS_MESSAGE_CODE.getMsg("添加"), type.getId());
    }
```

![image-20231016012922932](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231016012922932.png)

## final

public class Example {

```
public static void main(String[] args) {
    // 1. 修饰变量
    final int x = 10;
    // x = 20;  // 编译错误，不能修改 final 变量的值
    System.out.println(x);

    // 2. 修饰方法参数
    Example example = new Example();
    int result = example.add(5, 3);
    System.out.println(result);

    // 3. 修饰类
    FinalClass finalObject = new FinalClass();
}

// 修饰方法参数
public int add(final int a, final int b) {
    // a = 10;  // 编译错误，不能修改 final 方法参数的值
    return a + b;
}
```

}

// 修饰类
final class FinalClass {
    // 类的内容
}

#### 嵌入式

![image-20231021171924660](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231021171924660.png)

![image-20231021173217144](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231021173217144.png)

、

# Severlet、Cookie、Session 和 Filter 详解

Servlet（Server [Applet](https://so.csdn.net/so/search?q=Applet&spm=1001.2101.3001.7020)），全称 Java Servlet，未有中文译文。

## Servlet 的工作流程

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021071311003874.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0lUX19sZWFybmluZw==,size_16,color_FFFFFF,t_70)

![image-20231022223249197](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231022223249197.png)

# set集合

![image-20231023151551602](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231023151551602.png)

create table student(

stuno number(2) unique,

stuname varchar2(20) not null,--添加非空约束

sex char(2),

age number(2)

）;
drop table student

create table student(

stuno number(2) ,

stuname varchar2(20) ,--添加非空约束

sex char(2),

age number(2)

）;
alter table student modify stuno not null ;
alter table student add constraint uk_student_stuno unique(stuno)
alter table student add constraint uk_student_stuno unique(stuno) 
alter table student add constraint  pk_student_stuno_primary key(sex,age)
insert into student(stuno ,stuname ,sex,age) values (19,'list','男','22')
select * from student

create table student(
stuno number(2) primary key,
stuname varchar2(20),
sex char(2),
age number(2)
);
-- 表级约束

alter table student add constraint ck_student_sex_age check ((sex='男' and age>22) or (sex='女' and age>=20))

)

 create table dept (
 deptno number(2) primary key,
 dname varchar(20)
 );

 create sequence seq_dept 
 minvale 10,
 maxvalue 100,
 start with 10,
 increment 



   -- 序列：为dept中的主键deptno提供值
   create sequence seq_dept
   minvalue 10
   maxvalue 100
   start with 10
   increment by 1

 create table emp (
 empno number(4) primary key,
 ename varchar(20),
 deptno  int references dept(deptno)
 )

 

```
create table dept
```

   (
          deptno number(2) primary key,
          dname varchar(20)
          
         
   );

 -- 
 create table student (id int(8),name varchar(20),department varchar(20) ,index (id))ENGINE=InnoDB;
create table grade (Sid int(8),Cid int(10),score int,index(Sid),foreign key (Sid) references student(id) on  delete  restrict on update cascade)ENGINE=InnoDB;

--学生详情表

--学生表与学生详情表一对一
--班级与学生生 一对多
--学生与课程多对多
需要三张表
照片--学生详情表 一对一关系

create table studentmessage(
stuno number(20) primary key,
stuname varchar(20) not null ,
stuclass varchar(20) not null,
stucourseid varchar (20)not null
comment '学生详情'
)
create table student(
sno number(20),
sname number(20),
 --deptno  int references dept(deptno)


)



 

 

# StringUtils 中的各种is..Blank用法和is..Empty区别

### StringUtils.isBlank   【是否为空值（包含空格符）】

```
    StringUtils.isBlank(null) = true
    StringUtils.isBlank("") = true
    StringUtils.isBlank(" ") = true
    StringUtils.isBlank(“bob”) = false
    StringUtils.isBlank(" bob ") = false
    
    //与isEmpty()的区别
    StringUtils.isEmpty(null) = true
    StringUtils.isEmpty("") = true
    StringUtils.isEmpty(" ") = false
    StringUtils.isEmpty(“bob”) = false
    StringUtils.isEmpty(" bob ") = false
```

### StringUtils.isNotBlank 【是否真的不为空，相当于!isBlank】

public static boolean isNotBlank(final CharSequence cs) {
        return !isBlank(cs);
}



# 动态代理

## 代理

> 是一种常用的设计模式，其目的就是为其他对象提供一个代理以控制对某个对象的访问。代理类负责为委托类预处理消息，过滤消息并转发消息，以及进行消息被委托类执行后的后续处理。

# equalsIgnoreCase() 方法与equal对比

equals 会判断大小写区别，equalsIgnoreCase() 不会判断大小写区别：

```
import java.util.ArrayList;

public class Test {
    public static void main(String args[]) {
        String s1 = new String("today");
        String s2 = s1;
        String s3 = new String("today");
        String s4 = new String("TODAY");
        String s = new String("s;lfj");
        ArrayList<Object> objects = new ArrayList<>();
        boolean retVal;
        Boolean str;
        str = s1.equals(s2);
        System.out.println("返回值 = " + str);

        str = s3.equals(s4);
        System.out.println("返回值 = " + str);

        str = s1.equalsIgnoreCase(s4);
        System.out.println("返回值 = " + str);
    }
}
```

 "DROP TABLE Course" 和 "DELETE FROM Student," 是用于操作关系型数据库中的SQL语句，但它们有不同的用途和后果：

1. `DROP TABLE Course`：
   - 这个语句用于从数据库中删除整个表。在这种情况下，它将删除名为 "Course" 的表。
   - 当执行这个语句时，与 "Course" 表相关的所有数据、表结构以及相关的索引、约束和触发器都将被永久删除。
   - 这个操作是不可逆的，表和其中的数据将永远丢失，除非你有备份。
2. `DELETE FROM Student`：
   - 这个语句用于基于指定条件或无条件删除 "Student" 表中的特定行（或所有行）。
   - 当执行这个语句时，它会从 "Student" 表中删除数据，但表结构保持不变。
   - 数据的删除可以是有条件的，也就是你可以使用 WHERE 子句指定要删除的行。如果省略 WHERE 子句，它将删除 "Student" 表中的所有行。
   - 这个操作是可逆的，如果你有数据的备份，但它不会删除表本身。

总之，关键区别在于 "DROP TABLE" 删除整个表以及所有相关数据，而 "DELETE FROM" 从表中删除特定行，但保留表结构不变。选择哪个语句取决于你的具体需求，以及你是想删除数据还是整个表格。

你提供的两个语句, "DROP TABLE Course" 和 "DELETE FROM Student," 是用于操作关系型数据库中的SQL语句，但它们有不同的用途和后果：

1. `DROP TABLE Course`：
   - 这个语句用于从数据库中删除整个表。在这种情况下，它将删除名为 "Course" 的表。
   - 当执行这个语句时，与 "Course" 表相关的所有数据、表结构以及相关的索引、约束和触发器都将被永久删除。
   - 这个操作是不可逆的，表和其中的数据将永远丢失，除非你有备份。
2. `DELETE FROM Student`：
   - 这个语句用于基于指定条件或无条件删除 "Student" 表中的特定行（或所有行）。
   - 当执行这个语句时，它会从 "Student" 表中删除数据，但表结构保持不变。
   - 数据的删除可以是有条件的，也就是你可以使用 WHERE 子句指定要删除的行。如果省略 WHERE 子句，它将删除 "Student" 表中的所有行。
   - 这个操作是可逆的，如果你有数据的备份，但它不会删除表本身。

总之，关键区别在于 "DROP TABLE" 删除整个表以及所有相关数据，而 "DELETE FROM" 从表中删除特定行，但保留表结构不变。选择哪个语句取决于你的具体需求，以及你是想删除数据还是整个表格。

一、外键作用及其限制条件

1外键的定义
外键是某个表中的一列,它包含在另一个表的主键中。
外键也是索引的一种,是通过一张表中的一列指向另一张表中的主键,来对两张表进行关联。
一张表可以有一个外键,也可以存在多个外键,与多张表进行关联。

# 深入理解Java并发之synchronized实现原理

synchronized关键字最主要有以下3种应用方式，下面分别介绍

```
修饰实例方法，作用于当前实例加锁，进入同步代码前要获得当前实例的锁

修饰静态方法，作用于当前类对象加锁，进入同步代码前要获得当前类对象的锁

修饰代码块，指定加锁对象，对给定对象加锁，进入同步代码库前要获得给定对象的锁。
```

# HttpServletRequest 

# try catch

关联查询

lmda

## BeanUtils.copyProperties的用法(超详细，建议收藏)

我们如果有两个具有很多相同属性名的JavaBean对象a和b，想把a中的属性赋值到b，例如

- 接口中将接收到的前端请求参数XxxReqVo,我们想把这个入参转化为XxxQuery对象作为数据库的查询条件对象



### 应用案例

```
@Data
public class User {
    private String id;
    private String name;
    private String age;
    private String account;
    private String password;
}

@Data
public class Person {
    private String id;
    private String name;
    private String age;
    private String sex;
}

public class Test {
    public static void main(String[] args) {
        User user = new User();
        user.setId("1");
        user.setAge("2");
        user.setName("wzh");
        user.setAccount("wangzh");
        user.setPassword("1111");
        Person person = new Person();
        BeanUtils.copyProperties(user,person);
    }
}

Person(id=1, name=wzh, age=2, sex=null)

BeanUtils.copyProperties(source,target);
```

源对象source的属性拷贝值赋给目标对象target的过程中,属性名和属性类型都相同的属性才能被成功拷贝赋值，例如id,name,age这三个目标对象的属性被赋值成功，目标对象中的sex属性，由于源对象中没有同名的属性所以没法被赋值成功。
做赋值的属性一定要有对应的setter/getter才能成功赋值



#### 实例二

```
import org.springframework.beans.BeanUtils;

public class User extends Person{
    private Integer age;
    private String account;
    private String password;

    public <T> T getAge(Boolean isSon) {
        if(isSon == true) {
            return (T) this.age;
        }
    
        return (T) super.getAge();
    }
    
    //重载：方法名相同，但返回值数目/类型/不同类型返回值的顺序非一致，
    // setAge方法满足重载条件，getAge则无法满足重载条件
    public void setAge(String age) {
         super.setAge(age);
    }
    
    public void setAge(Integer age) {
        this.age = age;
    }
    
    public String getAccount() {
        return account;
    }
    
    public void setAccount(String account) {
        this.account = account;
    }
    
    public String getPassword() {
        return password;
    }
    
    public void setPassword(String password) {
        this.password = password;
    }
    
    public static void main(String[] args) {
        User user = new User();
        user.setId("1");
        // 设置父类的age属性值
        user.setAge("23");
        // 设置子类的age属性值
        user.setAge(2);
        user.setName("wzh");
        user.setAccount("wangzihan06");
        user.setPassword("123456");
    
        // 获取子类的age属性，子类的age属性是Interger类型，需要用Interger接收
        Integer age1 = user.getAge(true);
        System.out.println(age1);
        // 获取父类的age属性，子类的age属性是String类型，需要用String接收
        String age2 = user.getAge(false);
        System.out.println(age2);


        Person person = new Person();
        // 把子类对象user的属性值赋值给person,即把user对象中存储的Person父类相
        // 关的属性值赋给父类对象person
        BeanUtils.copyProperties(user,person);
    
        System.out.println("person:" +person.toString());
    
        // 反向赋值，即把person的name设置为null后赋值给user，那么user对象属性中继承自父类的这个
        // 属性name也会被重新赋值为空，但它自己所特有的属性比如account、password不会受影响
        person.setName(null);
        BeanUtils.copyProperties(person,user);
    
        System.out.println("user:" +user.toString());
    }
    
    @Override
    public String toString() {
        return "User{" +
                "age(User)=" + age +
                ", age(Person)=" + super.getAge() +
                ", account='" + account + '\'' +
                ", password='" + password + '\'' +
                ", name(Person)='" + super.getName() + '\'' +
                '}';
    }

}
```

![image-20231027190548585](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231027190548585.png)





```

```

## BeanUtils.copyProperties(userUpdateRequest, user);

![image-20231101160800937](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231101160800937.png)

![image-20231101231152885](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231101231152885.png)









![image-20231102183612742](C:\Users\l\AppData\Roaming\Typora\typora-user-images\image-20231102183612742.png)

看到很多[集合类](https://so.csdn.net/so/search?q=集合类&spm=1001.2101.3001.7020)实现了Serializable接口,Cloneable接口	

通过ObjectOutputStream 的writeObject()方法把这个类的对象写到一个地方（文件），再通过ObjectInputStream 的readObject()方法把这个对象读出来。

```
File file = new File("file"+File.separator+"out.txt");

FileOutputStream fos = null;
try {
    fos = new FileOutputStream(file);
    ObjectOutputStream oos = null;
    try {
        oos = new ObjectOutputStream(fos);
        Person person = new Person("tom", 22);
        System.out.println(person);
        oos.writeObject(person);            //写入对象
        oos.flush();
    } catch (IOException e) {
        e.printStackTrace();
    }finally{
        try {
            oos.close();
        } catch (IOException e) {
            System.out.println("oos关闭失败："+e.getMessage());
        }
    }
} catch (FileNotFoundException e) {
    System.out.println("找不到文件："+e.getMessage());
} finally{
    try {
        fos.close();
    } catch (IOException e) {
        System.out.println("fos关闭失败："+e.getMessage());
    }
}
                        
FileInputStream fis = null;
try {
    fis = new FileInputStream(file);
    ObjectInputStream ois = null;
    try {
        ois = new ObjectInputStream(fis);
        try {
            Person person = (Person)ois.readObject();   //读出对象
            System.out.println(person);
        } catch (ClassNotFoundException e) {
            e.printStackTrace();
        } 
    } catch (IOException e) {
        e.printStackTrace();
    }finally{
        try {
            ois.close();
        } catch (IOException e) {
            System.out.println("ois关闭失败："+e.getMessage());
        }
    }
} catch (FileNotFoundException e) {
    System.out.println("找不到文件："+e.getMessage());
} finally{
    try {
        fis.close();
    } catch (IOException e) {
        System.out.println("fis关闭失败："+e.getMessage());
    }
}
```

### [游标](https://so.csdn.net/so/search?q=游标&spm=1001.2101.3001.7020)的定义

Oracle游标（cursor）是一种数据结构，用于在PL/SQL代码中处理结果集，如用于暂时存储SELECT语句返回的结果集。游标允许程序员对结果集进行逐行处理，并在需要时检索或修改数据。当表的数据量很大的时候，不适合使用游标。

使用游标的5个步骤：

- 声明变量，用于保存SELECT语句返回的值。

- 声明游标，并指定SELECT语句。

- 使用`OPEN`语句打开游标。

- 通过`FETCH`语句从游标中获取记录。

- 通过`CLOSE`语句关闭游标。

  ```
  DECLARE
  MYRECORD employees%ROWTYPE;  /*声明变量*/
  CURSOR MYCUR IS
  SELECT * FROM employees;  /*声明游标*/
  BEGIN
  OPEN MYCUR;                    /*打开游标*/
  LOOP
  FETCH MYCUR INTO MYRECORD;  /*从游标中获取记录*/
  DBMS_OUTPUT.PUT_LINE (MYRECORD.NAME||'，'||MYRECORD.BIRTH);
  EXIT WHEN MYCUR%NOTFOUND;
  END LOOP;
  CLOSE MYCUR;                   /*关闭游标*/
  END;
  ```

  

**使用游标步骤：声明 打开 检索 关闭**

```oracle
DECLARE
    -- 声明变量
    v_position employees.position%TYPE;
    v_avg_salary NUMBER;
    

    -- 游标声明
    CURSOR position_cursor IS
        SELECT DISTINCT position
        FROM employees;

BEGIN
    -- 打开游标
    OPEN position_cursor;
    

 
    LOOP    -- 循环遍历职位
        -- 获取下一个职位
        FETCH position_cursor INTO v_position;
        EXIT WHEN position_cursor%NOTFOUND;
        
        -- 计算每个职位的平均工资
        SELECT AVG(salary) INTO v_avg_salary
        FROM employees
        WHERE position = v_position;
        
        -- 显示结果
        DBMS_OUTPUT.PUT_LINE('Position: ' || v_position || ', Average Salary: ' || v_avg_salary);
    END LOOP;
    
    -- 关闭游标
    CLOSE position_cursor;

END;
```

# 分配班级

```java
@Transactional(rollbackFor = {Exception.class})
@Override
public Result AddElTeach(ElTeachDTO elTeachDTO) {
    if (StrUtil.isBlank(elTeachDTO.getCourseId())) {
        return new Result(MddipEnum.COMMON_ERROR_MESSAGE.getCode(), MddipEnum.COMMON_ERROR_MESSAGE.getMsg("分配失败班级为空"));
    }

    List<String> classIds = Collections.singletonList(elTeachDTO.getClassId());
    for (int i = 0; i < classIds.size(); i++) {
        String classId = classIds.get(i);
        SysClass sysClass = sysClassMapper.getClassById(classId);
        List<ElTeach> elTeachList = elTeachMapper.queryTeachByCourseId(elTeachDTO.getCourseId(), classId);

        if (sysClass == null) {
            return new Result(MddipEnum.COMMON_ERROR_MESSAGE.getCode(), MddipEnum.COMMON_ERROR_MESSAGE.getMsg("分配失败班级不存在"));
        }

        if (elTeachList.size() > 0) {
            return new Result(MddipEnum.COMMON_ERROR_MESSAGE.getCode(), MddipEnum.COMMON_ERROR_MESSAGE.getMsg("分配失败该课程已被分配给" + classId + "班级请取消选择后重新添加"));
        }

        ElTeach elTeach = new ElTeach();
        elTeach.setId(IdUtil.simpleUUID());
        elTeach.setCourseId(elTeachDTO.getCourseId());
        elTeach.setClassId(classId);
        elTeach.setState("0");
        elTeach.setBeginTime(elTeachDTO.getBeginTime());
        elTeach.setEndTime(elTeachDTO.getEndTime());
        elTeach.setSchoolTime(elTeachDTO.getSchoolTime());
        elTeachMapper.AddElTeach(elTeach);
    }

    elTeachMapper.updateCourseTpe(elTeachDTO.getCourseId());
    return new Result(MddipEnum.SUCCESS_MESSAGE_CODE.getCode(), MddipEnum.SUCCESS_MESSAGE_CODE.getMsg("分配成功"));

}

/**
 * 分配教师
 */
@Override
public Result UpdateTeacher(List<UpdateTeachDTO> updateTeachDTOList) {
    for (UpdateTeachDTO updateTeachDTO : updateTeachDTOList) {
        SysTeacher sysTeacher = sysTeacherMapper.queryTeacherInfo(updateTeachDTO.getTeacherId());
        if (sysTeacher == null) {
            return new Result(MddipEnum.COMMON_ERROR_MESSAGE.getCode(), MddipEnum.COMMON_ERROR_MESSAGE.getMsg("分配失败该教师不存在!"));
        }
        elTeachMapper.GetTeacher(updateTeachDTO.getTeacherId(), updateTeachDTO.getId());
    }
    return new Result(MddipEnum.SUCCESS_MESSAGE_CODE.getCode(), MddipEnum.SUCCESS_MESSAGE_CODE.getMsg("分配成功"));
}
```

```
for (String teacher : elTeachDTO.getTeacherList()) {
    LambdaQueryWrapper<ElTeach> tp = new LambdaQueryWrapper<>();
    tp.apply("FIND_IN_SET({0}, teacher_id)", teacher)
            .eq(ElTeach::getCourseId, elTeachDTO.getCourseId());
    if (elTeachMapper.selectOne(tp) != null) {
        return ResultUtils.error("重复分配课程，此课程已被该位教师分配过~");
    }

}

tp.apply("FIND_IN_SET({0}, teacher_id)", teacher) 这部分代码使用了 apply 方法，这个方法允许在查询条件中添加自定义的 SQL 片段。在这个例子中，它使用了 MySQL 中的 FIND_IN_SET 函数，该函数用于在逗号分隔的字符串中查找某个值是否存在。

{0} 是一个占位符，会被后面的 teacher 参数所替换。
FIND_IN_SET({0}, teacher_id) 的作用是检查 teacher_id 字段中是否包含特定的教师 ID。
.eq(ElTeach::getCourseId, elTeachDTO.getCourseId()) 这部分代码使用了 eq 方法，它指定了一个相等的查询条件，以确保 courseId 与 elTeachDTO 中的 courseId 相匹配。
```
