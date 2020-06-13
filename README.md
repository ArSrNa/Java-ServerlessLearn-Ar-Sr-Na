# Ar-Sr-Na Java Serverless Learn项目-基础

## 教程介绍

Ar-Sr-Na，科普自媒体，业余无线电爱好者，擅长解决渲染IaaS问题

本教程面向Serverless开发，不针对本地开发，意味着需要有较好Java基础，英语基础，熟悉逻辑关系，了解Serverless架构。

## 教程初衷

在这个云计算盛行也是趋势的时代，本地函数带来的成本问题不占少数，尤其是当应用上线时，大量请求压榨服务器导致宕机，采购高性能服务器成本太高，所以Serverless出现了，效率更高，成本更低，扩展性，计算资源等层面具有众多优势，所以，它不香么？

创业路上并不是一帆风顺，我们也希望能帮助大家实现梦想，努力总比站在原地更接近成功！

# Serverless介绍

Serverless Computing，一种全新的函数架构，意味着无服务器，节省资源，也降低了成本。Serverless被称为FaaS（Function-as-a-Service），以平台即服务（PaaS）为基础，意味着需要一个平台来支撑函数服务。

本站建议使用腾讯云Serverless云函数服务[https://console.cloud.tencent.com/scf/](https://console.cloud.tencent.com/scf/)

# Java语言简介

java是计算机编程语言，不仅吸收了C++语言的各种优点，还摒弃了C++里难以理解的多继承、指针等概念，因此Java语言具有功能强大和简单易用两个特征。Java语言作为静态面向对象编程语言的代表，极好地实现了面向对象理论，允许程序员以优雅的思维方式进行复杂的编程。

Java功能强大，扩展性高，虽说在Java领域，专业的东西很多，未必一下子能理解完，

## 应用

无论是张浩扬的QQ程序，up主的数据可视化，都以java为后端程序，当然[bilibili数据可视化](https://github.com/ArSrNa/bilibiliData-TCV)这个是PHP的

### 项目在不断完善中，希望大家多多支持：QQ群：1097347557

# 新建函数

打开腾讯云的[云函数控制台](https://console.cloud.tencent.com/scf/)

![](https://ask8088-private-1251520898.cn-south.myqcloud.com/developer-images/article/3335308/gg4ureyez9.png?q-sign-algorithm=sha1&q-ak=AKID2uZ1FGBdx1pNgjE3KK4YliPpzyjLZvug&q-sign-time=1592035080;1592042280&q-key-time=1592035080;1592042280&q-header-list=&q-url-param-list=&q-signature=e1d3e3df9d9d1550ed566f822f5822b29758eb6d)

点击函数服务

![](https://ask8088-private-1251520898.cn-south.myqcloud.com/developer-images/article/3335308/93gzdy3koa.png?q-sign-algorithm=sha1&q-ak=AKID2uZ1FGBdx1pNgjE3KK4YliPpzyjLZvug&q-sign-time=1592035092;1592042292&q-key-time=1592035092;1592042292&q-header-list=&q-url-param-list=&q-signature=781a2a88847e4af22059f556e846e87422f43018)

新建一个函数

![](https://ask8088-private-1251520898.cn-south.myqcloud.com/developer-images/article/3335308/wi8vcnc8es.png?q-sign-algorithm=sha1&q-ak=AKID2uZ1FGBdx1pNgjE3KK4YliPpzyjLZvug&q-sign-time=1592035112;1592042312&q-key-time=1592035112;1592042312&q-header-list=&q-url-param-list=&q-signature=eeadda08cbf2eabe323a6faf63a80d59eee1ffed)

输入名称，语言选择Java，点击下一步

![](https://ask8088-private-1251520898.cn-south.myqcloud.com/developer-images/article/3335308/f3xxq8ogro.png?q-sign-algorithm=sha1&q-ak=AKID2uZ1FGBdx1pNgjE3KK4YliPpzyjLZvug&q-sign-time=1592035135;1592042335&q-key-time=1592035135;1592042335&q-header-list=&q-url-param-list=&q-signature=a8dff1ce26116145e70d8265c4836dc914f93595)

![](https://ask8088-private-1251520898.cn-south.myqcloud.com/developer-images/article/3335308/agmh0ztnjg.png?q-sign-algorithm=sha1&q-ak=AKID2uZ1FGBdx1pNgjE3KK4YliPpzyjLZvug&q-sign-time=1592035171;1592042371&q-key-time=1592035171;1592042371&q-header-list=&q-url-param-list=&q-signature=b00ac15a33310ddeb6b28768c070b278e3b6b816)

要注意此处的执行方法，它定义了调用云函数时需要从哪个文件中的哪个函数开始执行。

如上图是example.Hello::mainHandler

所以函数就得这么设置，从mainHandler开始执行：

```
public String mainHandler(KeyValueClass kv)
    {
       return String.format("Hello World");
    }
```

创建完成后，需要上传函数

![](https://ask8088-private-1251520898.cn-south.myqcloud.com/developer-images/article/3335308/yyy8ijr3a8.png?q-sign-algorithm=sha1&q-ak=AKID2uZ1FGBdx1pNgjE3KK4YliPpzyjLZvug&q-sign-time=1592035502;1592042702&q-key-time=1592035502;1592042702&q-header-list=&q-url-param-list=&q-signature=6b943f185fa9e0999834924a9641071e80249dd9)

需要把源代码改为index.java，然后打包为zip上传，就完成了
