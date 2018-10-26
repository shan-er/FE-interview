## JavaScript

- [概念相关](#概念相关)
    - [什么是闭包？用途？](#什么是闭包？用途？)
    - [什么是原型链？](#什么是原型链？)
    - [什么是深浅拷贝？](#什么是深浅拷贝？)
    - [sessionStorage,localStorage,cookie区别](#sessionStorage,localStorage,cookie区别)
- [编程相关](#编程相关)
    - [实现深拷贝](#实现深拷贝)



### 什么是闭包？用途？
**闭包是在某个作用域内定义的函数，它可以访问这个作用域内的所有变量。**

在javascript中，只有函数内部的子函数才能读取局部变量，所以<span style="color: #fcead8">闭包可以理解成“定义在一个函数内部的函数”</span>。

<span style="color: #fcead8">在本质上，闭包是将函数内部和函数外部连接起来的桥梁。</span>

闭包作用域链:
1. 函数本身作用域。
2. 闭包定义时的作用域。
3. 全局作用域。

闭包常见用途：
1. 创建特权方法用于访问控制
2. 事件处理程序及回调

闭包作用通俗的讲：一是可以读取函数内部的变量，另一个就是让这些变量的值始终保持在内存中，不会在这个作用域函数调用后被自动清除。

<span style="color: grey">关联点： 作用域 -> 作用域链</span>


### 什么是原型链？
**实例对象与原型之间的链接,叫做原型链。**

作用：用来实现共享属性和继承。

<span style="color: grey">关联点： 继承、对象（普通对象/函数对象）、构造函数</span>
<p style="color: grey">

    对象

    普通对象：
    - 最普通的对象：有__proto__属性（指向其原型链），没有prototype属性。
    - 原型对象(person.prototype 原型对象还有constructor属性（指向构造函数对象）)

    函数对象：
    - 凡是通过new Function()创建的都是函数对象。
        拥有__proto__、prototype属性（指向原型对象）。
        Function、Object、Array、Date、String、自定义函数。
        特例： Function.prototype(是原型对象，却又是函数对象)

</p>


### 什么是深浅拷贝？
浅拷贝针对对象中的基本类型的值生效，但是对引用类型中还有引用类型的情况就会失效。

深拷贝是针对对象中还有引用类型的情况，使用深拷贝可以使新创建的对象和原来的完全脱离关系。

深浅拷贝的区别，其实核心的关键点就是是**只复制了第一属性还是完全复制了所有的属性。**

<span style="color: grey">关联点： 变量类型（基本数据类型、引用数据类型）</span>


### sessionStorage,localStorage,cookie区别

1. 都会在浏览器端保存，有大小限制，同源限制
2. cookie会在请求时发送到服务器，作为会话标识，服务器可修改cookie；web storage用来存储客户端临时信息对象，不会发送到服务器
3. cookie有path概念，子路径可以访问父路径cookie，父路径不能访问子路径cookie
4. 有效期：cookie在设置的有效期内有效，默认为浏览器关闭；sessionStorage在窗口关闭前有效，localStorage长期有效，直到用户删除
5. 共享：sessionStorage不能共享，localStorage在同源文档之间共享，cookie在同源且符合path规则的文档之间共享
6. localStorage的修改会促发其他文档窗口的update事件
7. cookie有secure属性要求HTTPS传输
8. 浏览器不能保存超过300个cookie，单个服务器不能超过20个，每个cookie不能超过4k。web storage大小支持能达到5M或更大
9. web storage支持事件通知机制，可以将数据更新的通知发送给监听者。

<span style="color: grey">关联点： 离线缓存等</span>