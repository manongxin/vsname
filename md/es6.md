# 前端发展历程：



 1990 年，第一个Web浏览器的诞生；1991 年，WWW诞生，这标志着前端技术的开始。 

 1991年，Tim作为布道者在Internet上广泛推广Web的理念，与此同时，美国国家超算应用中心（National Center for Supercomputer Applications）对此表现出了浓厚的兴趣，并开发了名为Mosaic的浏览器，于1993年4月进行了发布。 



 1994年，html2规范发布



 1994年9月，因特网工程任务组（Internet Engineering Task Force）设立了HTML工作组。 



 1994年11月，Mosaic浏览器的开发人员创建了网景公司（Netscape Communications Corp.），并发布了Mosaic Netscape 1.0 beta浏览器，后改名为Navigator。 



 1995年，网景工程师Brendan Eich花了10天时间设计了JavaScript语言。起初这种脚本语言叫做Mocha，后改名LiveScript，后来为了借助Java语言创造良好的营销效果最终改名为JavaScript。网景公司把这种脚本语言嵌入到了Navigator 2.0之中，使其能在浏览器中运行。 



 与此相对的是，1996年，微软发布了VBScript和JScript。JScript是对JavaScript进行逆向工程的实现，并内置于Internet Explorer 3中。但是JavaScript与JScript两种语言的实现存在差别，这导致了程序员开发的网页不能同时兼容Navigator和Internet Explorer浏览器。Internet Explorer开始抢夺Netscape的市场份额，这导致了第一次浏览器战争。 



 1996年11月，为了确保JavaScript的市场领导地位，网景将JavaScript提交到欧洲计算机制造商协会（European Computer Manufacturers Association）以便将其进行国际标准化。 



 1997年6月，ECMA以JavaScript语言为基础制定了ECMAScript标准规范ECMA-262。JavaScript是ECMAScript规范最著名的实现之一，除此之外，ActionScript和JScript也都是ECMAScript规范的实现语言。自此，浏览器厂商都开始逐步实现ECMAScript规范。 





 1998年6月，ECMAScript2规范发布，并通过ISO生成了正式的国际标准ISO/IEC 16262 。 





 1999年12月，ECMAScript3规范发布，在此后的十年间，ECMAScript规范基本没有发生变动。ECMAScript3成为当今主流浏览器最广泛使用和实现的语言规范基础。 





 第一次浏览器战争以IE浏览器完胜Netscape而结束，IE开始统领浏览器市场，份额的最高峰达到2002年的96%。随着第一轮大战的结束，浏览器的创新也随之减少。 



 Google分别在2004年和2005年先后发布了两款重量级的Web产品：Gmail和Google Map。这两款Web产品都大量使用了AJAX技术，不需要刷新页面就可以使得前端与服务器进行网络通信，这虽然在当今看来是理所应当的，但是在十几年前AJAX却是一项革命性的技术，颠覆了用户体验。 





 Netscape于1998年被AOL收购前创建了Mozilla社区，Firefox于2004年11月首次发布，并且9个月内下载量超过6000万，获取了巨大的成功，IE的主导地位首次受到了挑战，Firefox被认为是Netscape的精神续作。 



 为了解决浏览器兼容性问题，Dojo、jQuery、YUI、ExtJS、MooTools等前端Framework相继诞生。 其中，jQuery独领风骚，几乎成了所有网站的标配。Dojo、YUI、ExtJS等提供了很多组件，这使得开发复杂的企业级Web应用成为可能。 



 HTML5草案发布不久，Google在2008年12月发布了Chrome浏览器，加入了第二次浏览器大战当中。Chrome使用了Safari开源的WebKit作为布局引擎，并且研发了高效的JavaScript引擎V8。 



 在第二次浏览器大战中，各个浏览器厂商都以提升JavaScript运行效率和支持HTML5各种新特性为主要目标，促进了浏览器的良性竞争。在这一场战争中，Chrome攻城略地，抢夺IE市场份额。2013年，Chrome超过IE，成为市场份额最高的浏览器。2016年，Chrome占据了浏览器市场的半壁江山。 



 2014年10月28日，W3C正式发布HTML 5.0推荐标准。 



 2008年Chrome发布，其JavaScript引擎V8的高效执行引起了Ryan Dahl的注意。2009年，Ryan利用Chrome的V8引擎打造了基于事件循环的异步I/O框架——Node.js诞生。 node.js允许我们脱离浏览器使用js。



npm是世界上最大的包模块管理系统



 Node.js也催生了node-webkit等项目，用JavaScript开发跨平台的桌面软件也成为可能。Node.js给开发人员带来了无穷的想象，JavaScript大有一统天下的趋势。 





# es6:

## 简介

ES6， 全称 ECMAScript 6.0 ，是 JavaScript 的下一个版本标准，2015.06 发版。

ES6 主要是为了解决 ES5 的先天不足，比如 JavaScript 里并没有类的概念，但是目前浏览器的 JavaScript 是 ES5 版本，大多数高版本的浏览器也支持 ES6，不过只实现了 ES6 的部分特性和功能。

## let与const

### 含义：

​	let 声明的变量只在 let 命令所在的代码块内有效。 var声明的变量作用于不清晰，不建议使用。

   const是常量的意思，const声明的变量只能赋一次值，而且不能发生任何改变。

### 代码：

```
{
let b = 20;
console.log(b);
}
// console.log(b);		//未定义


// const声明的变量，一定要给初始值
const name = "老王";  
name="小王";		//不被允许
console.log(name);  
```

## 解构赋值

```
解构数组
let [a,b,c] = ["赵","钱","吴"]
console.log(a,b,c)   //  赵 钱  吴

解构对象
let {name,age,addr} = {"name":"老王","age":18,"addr":"隔壁"}
console.log(name,age,addr)   //老王   18   隔壁

默认值，忽略,省略符(...)
```

## 函数默认值

很多函数里面，一些参数都会具有自己的默认值，es6里面简化了这个默认值的操作

```
下面这个函数unser的默认值为2,name的默认值为jack
function biaobai(unswer=2，name="jack"){
	
}
```

## map

map是一个键值对解构，他的每一个值由键和值组成，我们可以通过键来找到值。可以提高检索速度。

```
创建map键值对
let map = new Map()

赋值
map.set(key,value);    key与value都可以写任意内容，但是key通常是字符串

取值
map.get(key)

遍历map
map.forEach(function(value,key){
	console.log(key,value);
})

array转map
let arr = [["name","老王"] , ["age",21]]
let map = new Map(arr)

map转array
let arr = Array.from(map)
```

## Set

set里面的值不允许重复。

```
let set = new Set();
//存储数据
set.add(1);
set.add(3);
set.add(2);
set.add(1);
set.add(1);
console.log(set.size);   //重复的值根本插不进去

//遍历
for(s of set){
console.log(s)
}

let wang = new Set();
wang.add("小虹")
wang.add("小莉")
wang.add("小晶")

let zhao = new Set();
zhao.add("小虹")
zhao.add("小萍")
zhao.add("小基")

//并集，交集，差集
console.log("并集",new Set([...wang,...zhao]));

//交集
let ints = new Set([...wang].filter(function(x){
return zhao.has(x);
}))
console.log(ints);

//差集
ints = new Set([...wang].filter(function(x){
return !zhao.has(x);
}))
console.log("差集",ints);
```

## 不定参数

```
使用arguments对象也能获取所有的参数，arguments里面封装的是所有的参数。

function addAll(a,b,...canshu){
console.log(canshu);
}
addAll(5,5,6,6,7,8,9);
```

## 箭头函数

所谓箭头函数，其实就是对传统函数的一种简化写法。

```
标准转换
function(){}    ====              ()=>{}
		
一个参数，内容是一句话   
function(name){}                  name=>console.log("hello")

超过一个参数，箭头函数的小括号必须写，如果箭头函数的内容只有一个return语句，rentun可以省略不写
function add(a,b){return a+b;}    (a,b)=>a+b;
```

使用箭头函数，不会影响我们的this指向。

```
document.querySelector("button").onclick=()=>{
//箭头函数中的this不会改变指向，this不指向button
document.querySelector("button").style.backgroundColor="orange";
}
```

## Promise

promise有三种状态，分别是pendding，resolve，reject，代表等待，成功，还有失败状态。

简单的案例：

```
new Promise(function(resolve,reject){
    //第一个参数成功,第二个参数表示失败
    console.log("执行任务");
    resolve("恭喜你，成功了");

}).then((msg)=>{
	console.log(msg)
})
```



## async

异步语法糖。通过async与await的控制，能够很方便的控制异步执行流程。



async修饰函数，该函数默认会返回一个promise对象。

```
function get(page){
		return new Promise(function(resolve,reject){
			ajax("GET", page+".json", "", (shuju) => {
				。。。无所谓
				resolve();
			})
		})
	}

async function run() {
    await get(1);
    await get(2);
    await get(3);
}

run();
```

## 类型与对象

es6建议我们使用class关键字来创建类，通过new来创建对象，通过constructor来定义构造函数。其中，构造函数是是自动运行的，当我们new的时候，就会自动运行构造函数，其他的方法，“都”需要先创建出来对象，再通过对象去进行调用.

```
class Person{
		//构造器,构造函数,构造方法  --  构造器是一个特殊的函数，当我们创建(new)对象的时候，默认会调用这个构造器函数.
		constructor(name) {
		    this.name = name;
			console.log("我是构造器");
		}
		
		//实例方法，实例方法需要现有对象才能调用
		say(){
			console.log(`I am ${this.name}`);
		}
		drink=function(){
			console.log(`${this.name} 在喝水`)
		}
		age = 18;
	}
	let p = new Person("老王");
	p.say();
	p.drink()
	console.log(p.age);
```

## 继承

所谓继承就是子对象可以继承使用父对象的资源(属性，方法)

继承的关键字是extends，我们要注意的就是在子类中一定要在构造函数的第一行使用super关键字来调用父类的构造器，构造父类对象。

```
	class People{
		constructor(name) {
		    this.name = name;
			this.addr = "西京"
		}
		say(){
			console.log("say baba");
		}
	}
	
	//extends表示继承的意思
	class Woman extends People{
		constructor(arg,addr) {
			//super 父类     new Perple(arg)
		    super(arg);
			this.addr = addr;
		}
		/* say(){
			console.log("say er a")
		} */
	}
	
	let w1 = new Woman("大神","男京");
	console.log(w1.name,w1.addr);
	w1.say();
```

## 原型与原型链

所谓原型，其实就是创建对象的原本类型。我们可以通过操作原型来改变原本类型的一些特性，完成一些功能性的拓展。

原型链，可以通过对象的proto属性得到原型，也可以通过类的构造器使用prototype得到原型，我们又可以通过构造器创建出来对象，这样就好像一个链子，最后取出了原型链这样一个高大上的名字。

proto

prototype

## es5继承

### 原型继承

```
	function Person(name){
		this.name = name;
		this.eat=()=>{
			console.log("eat eat eat eat eat")
		}
	}
	
	function Woman(name){
		
		this.name = name;
	}
	
	let w1 = new Woman("嚣张")
	console.log(w1.name);
	w1.eat();
```



### 构造继承

```
function Person(name,addr){
		//woman他老爸的name
		this.name = name;
		this.addr = addr;
		this.eat=()=>{
			console.log("eat eat eat eat eat")
		}
	}
	

function Woman(name,addr){
	//打电话给Person的构造器，本质就是调用new Person  ，继承Person
	// Person.call(this,name,addr)
	Person.apply(this,[name,addr])
	//woman自己个儿的name
	this.name = "jack";
}

let w1 = new Woman("嚣张","北京")
console.log(w1.name,w1.addr);
w1.eat();
```

## 闭包

含义：

​		主要指的是在函数的内部创建函数，这样子的函数称之为闭包函数。

闭包函数可以使用外部函数的变量。而避免使用全局变量。

```
function f1(){
		let x = 10;
		let y = 20;
		console.log(x+y);
		return function f2(){
			console.log(x*y);
		}
	}
```

## 字符串

```
includes()			判断字符串中是否包含指定的内容

startWith()			判断字符串是否意自定的字符开头

endWith()			判断字符串是否以指定的字符结尾

padStart（）		  补全开头

padEnd()			补全结尾
```

















