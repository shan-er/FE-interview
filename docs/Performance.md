## 性能相关

- [如何对网站的文件和资源进行优化](#如何对网站的文件和资源进行优化)
- [为什么利用多个域名来存储网站资源会更有效](为什么利用多个域名来存储网站资源会更有效)

### 如何对网站的文件和资源进行优化
1. 文件/图片合并：减少http请求
2. 文件最小化/文件压缩：减少文件下载的体积
3. 使用CDN托管
4. 缓存的使用：nignx上开启gzip和缓存
5. gizp压缩你的js和css文件
6. 标签语义化：meta标签优化（title,description,keywords）、heading标签的优化、alt优化等
7. 反向链接，网站外链接优化
8. 避免重定向
<span>

    重定向就是用户请求的页面被转移到了别的地方，浏览器向服务请请求一个页面，服务器告诉浏览器请求的页面已经被转移到另外一个页面，并告知另一个页面地址，浏览器就再发送请求到重定向的地址。这样会增加服务器和浏览器之间的往返次数，影响网站性能。

    重定向状态码有：301永久重定向   302临时重定向。304 not modified  并不是真的重定向，它是用来告诉浏览器get请求的文件在缓存中，避免重新下载。
</span>

9. 将css放在页面最上面，将js放在页面最下面
<span>

    css放在页面最上面可以防止页面出现白屏、闪跳的现象，即减少页面的首屏出现时间。js的下载和执行会阻塞Dom树的构建（严谨地说是中断了Dom树的更新），所以script标签放在首屏范围内的HTML代码段里会截断首屏的内容。而且js中可能会对DOM节点进行操作，而这时代码是自上向下进行执行的，这样会造成js对相应的元素操作不了。所以js放在页面的最下面。
</span>

10. 其他


### 为什么利用多个域名来存储网站资源会更有效
1. CDN缓存更方便
2. 突破浏览器并发限制
3. 节约cookie带宽：跨域不会传cookie
4. 对于UGC的内容和主站隔离，防止不必要的安全问题
5. 节约主域名的连接数，优化页面响应速度
