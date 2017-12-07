### 项目坑----叙述文档

---
1. method的子方法不能使用es6中的()=>{}

``` bash
这是一个一般来说比较容易出现的问题，但也是相对比较容易找到的问题
```
---
2. v-for 循环缓存问题
> register.vue

``` bash
v-for中判别两组数据不同的依据是有不同的v-key的值
当两组不同数据使用相同的key值时会
出现现实上一组列表项的问题
因此每次列表修改过程中要注意对key值做出对应的改变

在这个项目的register页面中就为了这个缓存绞尽脑汁
一开始以为是computed方法带有缓存功能
结果换成watch方法还是出现如下问题
终于发现每一次的key的改变可以影响到被选择列表项的返回值
由此终于发现v-for的key值问题
```