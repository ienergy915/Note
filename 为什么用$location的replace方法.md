为什么用$location的replace方法
=============================

尼玛，发现自己对之前代码态度就是，遇到问题解决就好了，也不知道为什么这么做。然后我就遇到重复来重复去的bug!

#### bug场景：
  在NG中一载入页面的时候，用了`$location.path('/xxx');`跳转了，但是在客户端中，需要点击很多次返回键才会结束页面。
  
#### 解决bug
  `$location.path('/xxx').replace();` 
  
#### 问题来了，为什么用replace()就可以了呢？
  因为`replace`可以告诉`$location`服务下次自动和浏览器同步，上条浏览记录应该被替换而不是创建一个新的。


重定向会导致客户端回退有问题！
