# Node.JS



## 什么是node.js

运行在服务端的javascript，而不是运行在浏览器上面.

## node.js能做什么呢

+  部署一些高性能的服务 
+ 操作数据库
+ 文件管理系统
+ 模块管理系统

## node.js安装

```
官网下载安装一路回车即可
```

## npm包管理器

```
检测nodejs版本
node -v

检测npm版本
npm -v

安装包
npm install 包名

卸载包
npm uninstall 包名

```

## 跨域问题

所谓跨域问题，其实就是两个网站(包括不同域名或者不同端口或者不同ip),互相发送异步请求获取数据，就会发生跨域访问的问题，通常情况报错信息里面会有提示cors.碰到这个情况，我们可以使用如下方式解决。

方式一：

jsonp形式，结合jquery框架的ajax方法。

发送请求需要添加类型为jsonp

```javascript
$.ajax({
	url:"http://localhost:8081/",
	type:"post",
	dataType:"jsonp",     //////////////////////重点/////////////////////////
	jsonpCallback:"call",   //////////////////////重点/////////////////////////
	success:function(data){
		document.write(data);
	}
})
```
后台返回数据的时候，需要用call把他包裹起来

```
response.end("call('hello')")    //call必须和上面jsonpCallback后面的名字一致
```

## express框架

主要作用是帮我们使用javascript代码创建服务器。

### 创建服务器

```
var express = require('express');
var app = express();
app.listen(8081)
```

### 接收请求返回数据

```
get表示只能接收get请求，post表示只能接收post请求，all表示既能接收get，也能接收post请求
app.get("路径",function(req,resp){    
	//req表示请求，resp表示响应
	resp.send("数据");  //同步数据
	resp.send("call('异步数据')");  //异步数据
	resp.sendFile(__dirname+"/"+req.path)
})
```











