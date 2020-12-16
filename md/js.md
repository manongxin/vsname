几个常用的方法：
	节点(node)就是标签。

	根据节点的id获取节点
	document.getElementById()
	
	弹窗
	alert()
	
	控制台输出
	console.log()
	
	输出value值（输入框里面的值）
	let l = 节点.value;
	
	确认框
	prompt()
	
	打印内容到页面上
	document.write(输出的内容)


常量与变量：
​	常量：其值不能发生改变的量   (数字，字符串类型,布尔类型）
​	变量：其值可以发生改变的量   (整数类型，小数类型，布尔类型，字符类型，字符串类型)
​	
​		注意：
​		无论是变量还是数组都要先声明后使用。
​		变量的命名:首单词首字母建议小写，其他单词首字母大写   helloWorld 
​		           只能由字母，数字，下划线，$符组成	
​				   不能用数字开头


​			怎么判断值得类型
​			type of 值
​			
​			类型转换 
​				任何类型加上字符串就是字符串类型
​				
​				字符串转正数
​					parseInt(字符串)
​				字符串转小数
​					parseFloat(字符串)
​	
​	1.使用prompt框，提示用户输入名字，职业，车子
​					然后，等用户输入完成，我们就在页面上输出 ：   亲爱的工程师老王您好，您的宝马去吃草了。
​					名字，职业，车子都是变量，其它使用常量			


运算符：
​	算术运算符
​		+	-	*	/	%
​	
​	赋值运算符
​		=	+=	-=	*=	/=	%=	++		--
​	
​	比较运算符
​		==	>	<	>=	<=	!=	===		!===
​	
​	逻辑运算符
​		&&	||	!
​		
​		&&只要有一个为false，其结果一定为false，意味着第一个为false，后面不需要计算
​		||只要有一个为true，其结果就一定为true，意味着。。
​	
​	三目运算符
​		a=10?等了:不等		这个表达式的值要不是[等了]，要不是[不等]
​		
​		a为10，结果是就是等了
​		a不为10，结果就是不等

数组：
	数组是什么
		变量是一个容器，只能装一个值
		数组也是一个容器，能装很多值
		
	数组的结构：
		线性结构,通过下标指定每个值。
		
	怎么创建数组
		let arr01 = [];		
		let arr02 = new Array();


​	
​	怎么向数组赋值
​		arr01[0] = "小明"
​		arr02[3] = "小刚"
​	
​	怎么从数组取值
​		var n1 = arr01[0];
​		var n2 = arr02[3];
​	
​	练习:
​		数组。
​		提示用户录入名字，年龄，地址
​		再提示用户录入名字，年龄，地址 
​		再提示用户录入名字，年龄，地址 
​		...
​		
​		一共录入3次就行了，要求输出第二个人的信息。格式【18岁的小明，跟女朋友住在桥洞下面】
​		本题需要有3个数组，一个数组专门装名字，一个数组专门装年龄，一个数组专门装地址。
​		
​	迭代数组（遍历数组）：
​		使用某种方式查看数组中所有的值。
​			let names = ["张三","李四","王五","赵柳"]
​				
​			初中级别：
​				for(let i=0;i<names.length;i++){
​					names[i];
​				})
​				
​			高中级别：
​				for( x in names){
​					names[x]
​				}
​				
​			大学级别:
​				names.forEach(function(name,i){
​					//循环体
​					document.write(name+i+"<br/>")
​				})

if判断语句：
	例子：比如输入一个分数，如果分数小于40，输出不爱你，
	     如果分数小于60，加油，下次会及格的
		 如果分数小于80，你很棒，很不错
		 如果分数小于90，可以哦，很优秀
		 如果分数小于等于100，你爸张主任是不是给你泄题了啊？
		 
	let num = prompt("请录入你的分数");
	if(num < 40){
		console.log("不爱你，40都没有")
	}else if(num < 60){
		console.log("加油，下次争取及格")
	}else if(num < 80){
		console.log("你很棒，很不错")
	}else if(num < 90){
		console.log("哎哟，不错哦")
	}else{
		console.log("你爸张主任是不又给你泄题啦，哈哈")
	}


switch选择语句
	选择语句，有唯一确定的值可供选择，比如 1，2，3，4  比如A,B,C,D 
	比如页面上有一个菜单，A：选择角色		B：选择性别
				A:选择角色
					1.法师
					2.射手
					3.战士
					
				B:选择性别
					1.男神
					2.女神
					3.人妖
					
		code:
			document.write("<p>A:选择角色</p>")
			document.write("<p>B:选择性别</p>")
			let ans = prompt("请选择(A或B)");

循环语句：
	for(定义变量;控制范围;增量){循环体}

---------------------------------------------------------------------------------------------------------------------

循环的停止：
	自然死亡：
		控制变量的范围，使循环自然结束的方式。
		此种方式比较温和，效率比较好。但是不一定能满足所有的需求。
		
	意外死亡：
		装死（继续：continue）：
			当次循环余下的内容都不执行了，但是不会影响下一次循环。(这种死亡方式不会影响循环的整体次数)
			
		真死（退出：break）：
			退出当次循环，循环即刻停止。
			
		拖着全世界一起死(结束：return)，只能在函数中使用return.
		
	循环命名：
		HG:for(){
			
		}
		
		根据循环的名字来控制循环的停止
		break HG;
		continue HG;

==================================================================================================================
函数(方法)：
	什么是函数？
		是一对代码的合集。类似于工具。每个函数都有自己特定的功能。函数可以被其他人调用。
		
	怎么写函数：
		function 函数名(输入){
			//函数体，逻辑代码，完成函数功能
			return 输出内容;
		}


​		
​		function：国家规定
​		函数名：  自己定义，建议大家首单词首字母小写。 sayHi   hello 
​		输入：	  a,b	叫做型参，大家自己命名的，个数也是大家自己定义的。
​		输出：	  自己定，可以有输出，也可以不要输出。
​		
​	怎么用函数：
​		let rs = 函数名(实际参数1，实际参数2，实际参数3);
​		rs表示返回的值。
​		
​	特点：
		一次定义，n次受用。
==================================================================================================================		
	进制：
		计算机底层使用的是二进制。
		
		2进制：
			是由0和1组成的
			二进制				十进制
			0						0
			1						1
			10						2
			11						3
			100						4
			101						5
			110						6
			111						7
			1000					8
			1001					9
			1010					10
			1011					11
			1100					12
			1101					13
			1110					14
			1111					15
			10000					16
			
			规律：
				二进制转成十进制，从右往左数，第一个1表示1，第二个1表示2，低三个1表示4，第四个1表示8，第五个1表示16，第六个1表示32，其实就是2的(n-1)次方
	
			大家自己随意转2进制与10进制。
			
			1010101011111   -》10进制的值？（写出过程)


​			
​		
​		8进制：
​			由0，1，2，3，4，5，6，7
​		
​		10进制：
​			由0，1，2，3，4，5，6，7，8，9
​		
​		16进制：
​			由0，1，2，3，4，5，6，7，8，9，A,B,C,D,E,F
​			
​	==================================================================================================================
​	this:
​		含义：表示当前对象本身(自己的意思)
​		
​		this默认情况指向window。
​		
​	==================================================================================================================
​	dom:
​		dom是什么？
​			dom全称是document object model (文档对象模型)
​			
​			文档可以转成模型，模型是由无数的对象组成的，文档是由无数的节点组成的，对象其实就是节点。
​			我们操作html，其实就是操作对象，操作节点。
​		---------------------------------------------------------------------------------------------------------------
​		获取节点:
​			通过标签名找节点
​				let nodes = document.getElementsByTagName("标签名");
​				
​				注意：默认返回的是一个节点的数组，哪怕是只有一个，返回的也是数组。
​	
			通过id找节点
				let node = document.getElementById("id值");   //调用document对象的getElementById的函数，传进去id值，返回相对应的节点对象。
				注意：只能拿到符合要求的第一个节点
				
			通过name找节点
				
			通过class找节点


​			
​		事件:
​			事件本身其实已经存在了，只是别人不知道触发事件的时候需要做什么？所以需要我们自己的定义(监听,事件).
​			
​			如何绑定事件：
​				方式一：直接在html标签上面绑定  
​						<p on事件名="js代码">aa</p>
​						
​						案例1：
​						<p onclick="let a = prompt('美女约吗');if(a == 'ok'){alert('7天见')}">点我问候你女友</p>
​						
​						案例2：
​						<p onclick="yue()">点我问候你女友</p>
​						
​						<script>
​							function yue(){
​								let a = prompt('美女约吗');
​								if(a == 'ok'){
​									alert('7天见')
​								}
​							}
​						</script>
​						
​				解绑事件：
​					removeAttribute("onclick")
​						
​				方式二:通过js绑定事件
​						node.on事件名= yue;
​						function yue(){
​							
​						}
​						
				解绑事件：
					this.onclick=null;
						
				方式三：通过addEvenListener
						node.addEvenListener("事件名",function(){函数内容})
						
				解绑事件：
						node.removeEvenListener("事件名",函数名)
						
			事件的冒泡：
				含义：
					触发一个盒子上面的小盒子的某个事件，连带会触发大盒子的同一事件。
				解决：
					e.stopPropagation();
			
			常见的事件由哪些
	
				onclick					点击事件


​				
​				onblur					失去焦点				
​				onfocus					得到焦点
​				onchange				内容改变
​				(省市联动)
​				
​				keydown					键盘按下去
​				keyup					键盘弹起来
​					
​					通过keycode判断是按得哪一个键。(函数默认可以传递一个叫做e的参数，每一个按钮都对应一个键盘码头keyCode)
​					对照表：https://www.cnblogs.com/lxwphp/p/9548823.html
​					
​					组合键
​					ctrl+shift
​					e.ctrlKey && e.keyCode == 17 
​					
​					ctrl+enter
​					e.ctrlKey && e.keyCode == 13
​				
​				oncontextmenu			右键事件
​					
​				ondblclick				双击事件
​				
​				onmousedown				鼠标点下去
​				onmouseup				鼠标松开
​				onmouseover				鼠标放上去
​				onmouseout				鼠标离开
​				onmousemove				鼠标移动
​					
				ondragStrat				开始拖动
				ondrag					正在拖动
				ondragEnd				结束拖动
				
				ondragEnter				拖进来了
				ondragLeave				拖出去了
				ondragOver				拖在目标里面晃来晃去
				ondrop					在目标位置松开了拖拽物，默认不执行，需要ondragLeave返回false，才会执行
				
		阻止默认事件：
			e.prventDefault();			


​				
​			
​		
​		操作：
​			内容操作
​				innerHTML			表示两个标签中间的那部分内容
​									
​					获取内容			let v = node.innerHTML;
​					替换内容			node.innerHTML="内容";
​					追加内容			node.innerHTML+="内容";
​				
​				操作value，其实是因为输入框的值默认和节点的value属性的值进行绑定了。
​				value
​					获取value		node.value	
​					设置value		node.value="新的值";
​			
​			属性操作：
​				读取属性：
​					获取指定属性的值
​						方法一：
​							let 属性值 = node.getAttribute("属性名")
​							
​						方法二:
​							let id值 = node.id;		(name属性不行)
​					
​				修改属性：
​						
​					修改指定属性的值
​						方法一：
​							node.属性="值";
​							
​						方法二:
​							node.setAttribute("属性","值");
​					
				增加属性：
					oImg.setAttribute("class","bcred");
				
				删除属性：
					node.removeAttribute("属性名");
			
			样式操作：
				从字面意思理解，就是操作style的值。但是我们这里说的操作样式，其实是指操作class
				属性的值。因为class里面通常就是用来表示样式的。
				
				获取样式：
					以前的方式：	let cname = node.className;
					h5:			let cname = node.classList;
					
				添加样式：
					h5：node.classList.add("a");
					
				删除样式：
					h5: node.classList.remove("class");
					
				修改样式:
					以前的方式:	node.className="a b";  覆盖效果
					h5:			node.classList.replace("old","new");
			----------------------------------------------------------------------------
			节点操作：
				创建节点：
					let 节点 = document.createElement("节点的名称");
					
				添加节点：
					node.appendChild("节点");   为node节点添加一个新的子节点
					
				删除节点：
					node.remove();
					
				替换节点：
					parentNode.replaceChild(new,child);
					
				克隆节点：
					node.cloneNode(true) 
					
					true表示克隆节点本身，以及字节点
					false表示只克隆自己，肤浅
	-------------------------------------------------------------------------------------
	错误处理：
		try{
			//尝试运行的代码
		}catch(err){
			//报错之后运行的代码
		}finally{
			//无论是否报错都需要运行的代码
		}
	-------------------------------------------------------------------------------------
	定时器：
		含义：
			跟闹钟一样，但是js里面的定时器表示每隔多长时间就执行一遍什么代码。
			
		语法：
			创建定时器:
				obj = setInterval(代码,间隔时间)
			清除定时器:
				clearInterval(obj)
				
		案例：每隔3秒页面输出一行hello
		    obj = setInterval(sayHello,3000)
			function sayHello(){
				document.write('hello')
			}
	-------------------------------------------------------------------------------------
	延时器:
		含义：
			跟定时器不同，延时器表示延迟一段时间之后执行某段代码，不具备重复性。
		
		语法:
			创建延时器
				obj = setTimeout(代码,延迟时间)
	
			清除延时器:
				clearTimeout(obj)
				
		案例：
	-------------------------------------------------------------------------------------
	内置对象：
		javascript为我们提供了很多内置对象。下面为为大家介绍几个常用的内置对象。
			布尔型可以是一个对象。
			数字型可以是一个对象。
			字符串也可以是一个对象
			日期是一个对象
			数学和正则表达式也是对象
			数组是一个对象
			甚至函数也可以是对象
			
		Boolean：
			创建布尔类型
				let b = new Boolean(0);
			
			如果布尔对象无初始值或者其值为:
				0
				-0
				null
				""
				false
				undefined
				NaN
				结果就为false，其他为true
			
		Number:
			属性：
				Number.MAX_VALUE	最大值
				Number.MIN_VALUE	最小值
				Number.NaN	非数字
				Number.NEGATIVE_INFINITY	负无穷，在溢出时返回
				Number.POSITIVE_INFINITY	正无穷，在溢出时返回
				Number.EPSILON	
				表示 1 和比最接近 1 且大于 1 的最小 Number 之间的差别
				
				Number.MIN_SAFE_INTEGER	最小安全整数。
				Number.MAX_SAFE_INTEGER	最大安全整数。
				
			功能:
				Number.parseFloat()	将字符串转换成浮点数，和全局方法 parseFloat() 作用一致。
				Number.parseInt()	
				将字符串转换成整型数字，和全局方法 parseInt() 作用一致。
				
				Number.isFinite()	判断传递的参数是否为有限数字。
				Number.isInteger()	判断传递的参数是否为整数。
				Number.isNaN()	判断传递的参数是否为 isNaN()。
				Number.isSafeInteger()	判断传递的参数是否为安全整数。
		String:
			属性：
				length			长度
				
			方法：
				charAt()		返回在指定位置的字符。
				concat()		连接两个或更多字符串，并返回新的字符串。
				substr()		从起始索引号提取字符串中指定数目的字符。
				substring()		提取字符串中两个指定的索引号之间的字符。
				indexOf()		返回某个指定的字符串值在字符串中首次出现的位置。
				lastIndexOf()	从后向前搜索字符串，并从起始位置（0）开始计算返回字符串最后出现的位置。
				includes()		查找字符串中是否包含指定的子字符串。
				repeat()		复制字符串指定次数，并将它们连接在一起返回。
				replace()		在字符串中查找匹配的子串， 并替换与正则表达式匹配的子串。
				slice()			提取字符串的片断，并在新的字符串中返回被提取的部分。
				split()			把字符串分割为字符串数组。
				startsWith()	查看字符串是否以指定的子字符串开头。
				toLowerCase()	把字符串转换为小写。
				toUpperCase()	把字符串转换为大写。
				trim()			去除字符串两边的空白
				toString()		返回一个字符串。
				valueOf()		返回某个字符串对象的原始值。
				toLocaleLowerCase()	根据本地主机的语言环境把字符串转换为小写。
				toLocaleUpperCase()	根据本地主机的语言环境把字符串转换为大写。
				match()			查找找到一个或多个正则表达式的匹配。
				charCodeAt()	返回在指定的位置的字符的 Unicode 编码。
				fromCharCode()	将 Unicode 编码转为字符。
				search()		查找与正则表达式相匹配的值。
		
		Array:
			含义：
				数组的意思。数组跟变量不一样，他可以装很多的数据。
				
			属性：
				length				获取数组的长度


​					
​			方法：
​				concat()			把多个数组合并成一个数组
​				copyWithin(tar,start,end)	把src位置的值拷贝到tar位置，替换原有值
​				fill(value)			将数组的所有位置的初始值设置成value
​				filter(callback)	过滤函数，可以从数组中筛选出我们想要的内容
​				forEach(callback)	迭代数组
​				includes(a)			判断数组中是否包含a
​				indexOf()			返回数组中指定元素的位置
​				lastIndexof()		返回数组中指定元素的位置，从最后一位开始搜起
​				Array.isArray(c1)	判断c1是否是数组
​				join(separator)		获取数组的所有内容使用分隔符连接成一个字符串
​				map(callback)		处理数组中的数据，返回一个处理后的新的数组
​				pop()				那数组的最后一个值，原数组就少了一个值
​				shift()				拿数组的第一个值，原数组就少了一个值
​				
​				push()				向数组的最后一位放一个值
​				reduce(callback)	将数组元素计算为一个值
​				reverse()			翻转数组
​				slice()				选择数组的一部分，返回一个新的数组
​				sort()				排序的
​				splice(index,count,value)		将index位的count个值删除，替换成value
​				
​		Date:
​			含义：
​				表示日期
​			
​			我们可以通过Date来操作时间。
​			
​			获取当前时间
​				let t = new Date();
​			
​			获取当前年份
​			
​			获取当前月份
​			
​			获取当前天数
​			
			获取当前小时
			
			获取当前分钟
			
			获取当前秒钟


​			
​		Math:
​			含义：
​				表示数学函数，里面封装了一些跟数学相关的一些操作
​				
​			属性：
​				PI			圆周率
​			
​			方法：
​				abs(x)		获取绝对值
​				ceil(x)		对数进行上舍入
​				floor(x)	向下取整
​				max()		取最大值
​				min()		取最小值
​				pow(x,y)	计算x的y次方
​				random()	获取0-1之间的随机数
				round(x)	四舍五入
=======================================================================================================
	元素的宽高：
		内容的宽高
			node.style.width
			node.style.height
			
		内容+内间距:  (只读)
			node.clientWidth
			node.clientHeight
			
		内容+内间距+边框:(只读)
			node.offsetWidth
			node.offsetHeight
		
		滚动宽高:
			scrollWidth
			scrollHieght
			
			作用跟clientWidth类似


​		
​		
​			
​	=======================================================================================================		
​	元素的距离：
​		获取元素跟他爹的距离(爹一定要有钱“带定位属性的”)
​		node.offsetLeft
​		node.offsetTop
​		
​		获取滚动距离
​		document.documentElement.scrollTop
​		document.body.scrollTop


​		
​		鼠标相关距离:
​			鼠标距离x轴的距离(包含滚动距离)
​			e.pageX
​			
​			鼠标距离x轴的距离(不包含滚动距离)
​			e.clientX
​		
​			获取显示器的距离
​			e.screenX
​			
​			获取事件源的距离
​			offsetX 

=======================================================================================================
json:
	其实是一种数据格式。
	他里面约定中括号表示数组。							[]
	大括号表示对象，对象与对象之间用逗号隔开。			{}
	对象由属性组成,两个属性之间用逗号隔开。				{a:"aaf",b:12,c:true}
	属性由属性名和属性值组成。							
			
	[
		{},
		{}
	]
=======================================================================================================
正则表达式：
	含义：
		正则表达式本质上就是一个对象，这个对象具有下面的两种功能。
	功能：
		1.搜索
		2.验证
	
	如何创建正则表达式：
	
		let patt = new RegExp("表达式具体的内容");
		
		或者更简单的方式:
		
		let patt = /pattern/;
	
	使用步骤：
		1.创建规则 --  描述要匹配的内容(比如长度在5到10个之间，只能是小写字母)
		2.创建正则表达式对象   /规则/
		3.调用对象的匹配的方法,将要匹配的字符串传给它，他就会自动将字符串与表达式进行匹配，返回true或者false
		
	匹配的方法:
		test()
		
		/e/.test("hello")
		
	匹配规则(表达式):
		/e/				只要包含了e就ok
		/[abc]/			只要包含了a或者b或者c都行
		/[A-Z]/			一定要包含大写字母
		/[a-zA-Z0-9]/	只要包含任意大小写字母或者数字都成立
		/^a$/			只有值为a才成立
		/^[A-Z]/
		/^孙/			判断是否姓孙
		/发/			只要包含发就ok了
		/^[a-z]{3}$/	只能是3个小写字母
		/^[a-zA-Z0-9]{5,8}$/	只能是5到8个子母数字
		/red|blue|yello/只要包含了其中的任意一个都成立

============================================================================
	BOM:
		browser Object 	Model   浏览器对象模型。
		
	window(窗口的意思)
		弹出一个窗口
		open("要打开窗口的路径",200,300)
		
		关闭ck窗口(默认关闭当前窗口)
		ck.window.close()
		
	Screen(屏幕的意思):
		screen.availWidth - 可用的屏幕宽度
		screen.availHeight - 可用的屏幕高度
		
	Location(位置的意思):
		// location.href="http://www.baidu.com"
		// location.hostname 返回 web 主机的域名
		// location.pathname 返回当前页面的路径和文件名
		// location.port 返回 web 主机的端口 （80 或 443）
		// location.protocol 返回所使用的 web 协议（http: 或 https:）
			
	History(历史对象):
			history.back()		后退
			history.forward()	前进
			history.go(-2)		后退两步
			history.go(3)		前进3步


​	
​	Navigator(浏览器对象)
​	
​			navigator.userAgent		用户代理，区别不同的浏览器


​			
​			浏览器代号: " + navigator.appCodeName + "</p>";
​			浏览器名称: " + navigator.appName + "</p>";
​			浏览器版本: " + navigator.appVersion + "</p>";
​			启用Cookies: " + navigator.cookieEnabled + "</p>";
​			硬件平台: " + navigator.platform + "</p>";
​			用户代理: " + navigator.userAgent + "</p>";
​			用户代理语言: " + navigator.systemLanguage + "</p>";
​		
​	web存储：
​		含义：
​			把数据保存在浏览器的缓存里面。
​		
​		localStorage
​			特点;
​				用于长久保存整个网站的数据，保存的数据没有过期时间，直到手动去除
​				
​			保存(修改)数据：
​				localStorage.name="张三丰"
​				localStorage.setItem("name","张三丰")
​			
​			获取数据：
​				localStorage.name
​				localStorage.getItem("name")
​			
​			删除数据：
​				localStorage.remove("name")
​	
​			删除所有数据：
​			localStorage.clear();
​				
​			得到某个索引的key：
​			localStorage.key(index);


​			
​		sessionStorage
​			特点:
​				用于临时保存同一窗口(或标签页)的数据，在关闭窗口或标签页之后将会删除这些数据
​				
​			方法同上！
​	==================================================================================================
​	
​	面向对象：
​		
​		一句话：万物皆对象。
​		
​		已经使用过的对象：
​			Array,String,Date,Math,Number,Boolean,JSON...
​			
​		自己定义对象：
​			对象的作用：
​				变量，能保存一个值
​				数组，能保存多个值
​				对象，能同时保存多个变量，多个数组，乃至多个对象。
​		
​			描述对象(定义对象)
​				对象 = 对象的名字，对象的属性，对象的方法
​				
​				function Person(){
​					Person.name="jack"
​					Person.age=18;
​				}
​			
			创建对象
				使用对象一定要先创建对象
				
				let p1 = new Person();
				let p2 = new Person();
		
				//使用对象
				
				操作对象属性(读取值和设置值)
				
				操作对象的方法(调用方法)
				
	============================================================================================
	请求：
		请求组成：
			http://www.baidu.com:80/page/index?cl=3&tn=baidutop10
			
			http:					协议    
			www.baidu.com			域名（ip地址)
			:80						端口号
			page					表示page文件夹
			index					表示index文件
			?cl=3					带了一个参数，名字叫做cl，值是3
			&tn=baiduTop10			又带了一个参数，名字叫做tn,值是baiduTop10


​		
​			协议：
​				http：
​				https：
​				
​		请求方式：
​				GET
​							1.请求参数跟在路径后面
​							2.请求参数的大小限制在2kb
​				POST
​							1.请求参数不在路径后面
​							2.请求参数大小理论上无限制。
​							
​		响应状态码：
​			200				一切ok
​			201				表示创建
​			302				重定向
​			304				使用缓存
​			400				失败的请求
​			403				没有权限
​			404				资源不存在
​			405				请求方式不存在
​			408				请求超时
​			5，6			都是指服务器错误


​			
​		
​		同步请求：
​			种类：
​				<a href="请求路径"></a>						默认发送get请求
​				<form action="请求路径 method="get">			请求方式由method里面的值来决定，可get，可post
​					<input type="submit" value="提交"/>
​				</form>
​				可以在浏览器的地址栏直接输入网址(访问路径)		默认发送get请求
​				window.open("请求路径")						默认发送get请求
​				location.href="请求路径";					默认发送get请求
​		
​			特点：
​				请求过程中可能会卡死页面。
​				请求结果直接在页面上展示。


​				
​		异步请求:
​			原理：
​				使用ajax引擎发送异步请求，监听ajax引擎，获取请求结果
​				
​			特点：
​				请求过程不会卡死页面
​				请求结果不会直接展示在页面，需要主动获取。
​				
​			请求代码：
​				//发送异步发请求
​				function ajax(method,url,data,call){
​					
​					//创建一条狗--ajax引擎
​					let xhr = new XMLHttpRequest();
​					
​					//设置骨头的方位
​					xhr.open(method,url);
​					// xhr.open("GET","https://www.baidu.com/rec?platform=wise&ms=1&lsAble=1&rset=rcmd&word=%E7%99%BE%E5%BA%A6%E7%99%BE%E7%A7%91&qid=11197444350115079500&rq=%E7%99%BE%E5%BA%A6%E7%99%BE%E7%A7%91&from=844b&baiduid=7E376D594625E69CD9854300AC1D4A2A%3AFG%3D1&tn=&clientWidth=400&t=1597636916416&r=7970");
​					
​					 // 如果想要使用post提交数据,必须添加此行
​					//如果是post请求才有下面这一行代码
​					if(method && method == "POST"){
​					  xhr.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
​					  xhr.send(data);
​					}else{
​						 xhr.send();
​					}


​					
​					//检查狗是否完成任务--创建监听
​					xhr.onreadystatechange=function(){
​						/*
​						0: 请求未初始化
​						1: 服务器连接已建立
​						2: 请求已接收
​						3: 请求处理中
​						4: 请求已完成，且响应已就绪
​						*/
​						if(xhr.readyState == 4){
​							//请求已完成，数据已就位
​							if(xhr.status == 200){
​								//只有响应状态码是200我们才能正常获取数据，不是200，就算失败
​								
​								return call && call(xhr.responseText);
​							}
​						}	
​					}
​				}


​				
​			调用：
​				ajax(
​						//请求方式
​						"GET",   
​						//请求路径
​						"http://www.51houniao.com/product/banner/getBySeller/4bc4027c645343f09a964b5c2e9f875b?bannerType=2",
​						//请求参数   post请求才有
​						null,
​						//请求成功的回调函数
​						function(data){
​							console.log(data);
​							document.write(JSON.parse(data)[0].proTitle)
​						}
​					) 
​	需要有一台服务器：
​		
​		phpstudy:
​		
​	第一步：
​		<?php
​		// PHP 代码
​		?> 
​				
​	输出语句：
​		echo "Hello World!"; 
​		
​	函数,判断，循环 同js
​			
​	接收get请求的数据（页面传递给后台的参数)
​		$name = $_GET["参数名"];


​		
​	接收post请求的数据
​		$name = $_POST["参数名"]


​		
​	sql语句：
​		select * from student;     获取student表的所有数据


​		
​	php连接数据库:
​		第一步：创建连接对象
​			$conn = new mysqli(
​				"数据库所在的ip或者域名localhost127.0.0.1",
​				"用户名",
​				"密码",
​				"数据库名字"
​			)
​		
​		第二步: 使用连接对象向数据库发送数据操作请求（请求内容其实是一句话 sql语句)
​			$data = $conn->query("查询语句  select * from student");
​			
​		第三步:解析结果
​			3.1		获取数据的条数
​			      $len = $data->num_rows;
​				  
​			3.2     使用循环拿取每一行的数据
​				  //$row = $data->fetch_assoc();

​				for($i=0;$i<$len;$i++){
​					$row = $data->fetch_assoc();
​					//拿到一行数据之后，其实每一行又有多个数据,是数组类型
​					//获取单个数据
​					$row['name']   $['pwd']
​					
​				}
​	
​	HTML:
​		p
​		a
​		h1
​		span
​		img
​		form
​		table
​		ul
​		
​		15172735849
​

# css3

## 选择器：

​			*			通配符选择器
​			e			标签选择器
​			.class		类选择器
​			#id			id选择器
​			e,f			并联选择器		e和f标签
​			e>f			层级选择器		e里面的f
​			e+f			e后面的第一个f
​			e~f			e后面的所有f
​			e[attr]				带有attr属性的e标签
​			e[attr=a]			带有attr属性，且属性值等于a的e标签
​			e[attr~=a]			带有attr属性，且attr属性的值带有a的e标签
​			e[attr|=a]			带有attr属性，且attr属性的值以a-开头的e标签
​			e[attr^=a]			带有attr属性，且attr属性的值以a开头的e标签
​			e[attr$=a]			带有attr属性，且attr属性的值以a结尾的标签
​			e[attr*=a]			带有attr属性,只有attr属性包含a这个值即可。
​			e:first-child		选择第一个e元素，如果不是e，就没有效果
​			:last-child			选择最后一个
​			:only-child			选择独生子
​			:nth-child(3)		第三子，排行老三的节点
​			:nth-last-child(2)	倒数第2个
​			e:first-of-type		选择第一个e元素，如果第一个不是，就找第二个，找到为止。
​			e:nth-of-type(3)	选择第3个e元素，如果没有继续找
​			:only-of-type		
​			:nth-last-of-type
​			:lang(ab)			带有lang属性且值为ab的
​			:before				前置伪元素
​			:after				后置伪元素
​			:first-letter		选择第一个字符
​			:first-line			选择第一行
​			:root				选择文档的根节点(通常是指html节点)
​			:empty				选择空元素
​			:not()				取反
​			:target				选择目标
​			:enabled			选择所有不带disabled属性的
​			:disabled			选择所有带disable属性的
​			:checked			选择所有选中的
​			
​		以上所有的选择器，都可以用在js查找节点黎明
​			docuemnt.querySelect(选择器);
​			

## 	边框：

​		边框的半径：
​			border-radius
​				/* 四个角的半径都是50pxssss */
​				border-radius: 50px;	
​				/* 左上，右下都是10px， 右上，左下都是30px*/
​				border-radius: 30px 50px;
​				/* 左上，右上左下，右下 */
​				border-radius: 28px 82px 137px;
​				/* 左上，右上，右下，左下 */
​				border-radius: 10px 20px 30px 40px;
​				/* x轴：左上右上右下左下/y轴:左上右上右下左下 */
​				border-radius: 100px 92px 42px 42px /119px 119px 31px 31px;
​			
​			box-shadow：
​				盒子阴影
​				box-shodaw:x轴  y轴  模糊程序   阴影距离   颜色,x轴  y轴  模糊程序   阴影距离   颜色,...;

## 	背景：			

		可以插入多个背景(background);
		
			background-image:		背景图片
			background-size:		背景大小
			background-position:	背景位置
			background-repeat:		背景平铺
			background-origin:		规定背景图片的定位区域
			background-clip：		背景的裁剪
							border-box:		包括下边框背景
							padding-box:	包括内间距
							content-box:	只保留内容部分的背景
							
	渐变：
		线性渐变（Linear Gradients）- 向下/向上/向左/向右/对角方向
		
			方向：
				to	left
				to	right
				to	top
				to	bottom
				角度	度数deg
		
		径向渐变（Radial Gradients）- 由它们的中心定义
			
			重复的径向渐变：
				repeating-radial-gradient() 函数用于重复径向渐变：
							
	============================================================================================					
	文本效果：
		文本阴影：
			text-shadow
			
						x轴，y轴，模糊程度，颜色
			text-shadow: 5px 1px 2px red,7px 3px 2px yellow
			
		文本溢出
			text-overflow
				text-overflow: ellipsis;			省略号
				overflow: hidden;					超出隐藏
				/* 强制文本不换行 */
				white-space: nowrap;
		
		文字包裹
			word-wrap
				word-wrap:break-word;				在单词内部直接换行
	============================================================================================
	
	2D:
		
		平面：
		
			transform(缩放，倾斜，平移，旋转)
		
				缩放(scale()):
				
				倾斜(skew())：
				
				平移(translateX,translateY)：
				
				旋转(rotate())：
				
	3D:
		跟2D相比主要是多了一个z轴
				z轴平移
					
				z轴旋转
				
			transform-origin	允许你改变被转换元素的位置。设置基点
			transform-style		规定被嵌套元素如何在 3D 空间中显示.   显示3d效果
			perspective			规定 3D 元素的透视效果,景深
			
			perspective-origin	规定 3D 元素的底部位置。
			
			backface-visibility	定义元素在不面对屏幕时是否可见。


​		
​			
​	过渡:


​		
​		transition	简写属性，用于在一个属性中设置四个过渡属性


​		transition-property	规定应用过渡的 CSS 属性的名称
​		transition-duration	定义过渡效果花费的时间。默认是 0
​		transition-timing-function	规定过渡效果的时间曲线。默认是 "ease"
​		transition-delay
​			
​	动画：
​			@keyframes	规定动画。	
​			
​			animation	所有动画属性的简写属性。	
​			
​			animation-name	规定 @keyframes 动画的名称。	
​			
​			animation-duration	规定动画完成一个周期所花费的秒或毫秒。默认是 0。	
​			
​			animation-timing-function	规定动画的速度曲线。默认是 "ease"。	
​			
​			animation-fill-mode	规定当动画不播放时（当动画完成时，或当动画有一个延迟未开始播放时），要应用到元素的样式。
​					backwards	动画将应用在 animation-delay 定义期间启动动画的第一次迭代的关键帧中定义的属性值。
​					both	动画遵循 forwards 和 backwards 的规则。也就是说，动画会在两个方向上扩展动画属性。
​					forwards	在动画结束后（由 animation-iteration-count 决定），动画将应用该属性值。
​		
​			animation-delay	规定动画何时开始。默认是 0。	3
​			animation-iteration-count	规定动画被播放的次数。默认是 1。	3
​					n		可以写任意次数
​					infition无限循环
​					

			animation-direction	规定动画是否在下一周期逆向地播放。默认是 "normal"。	3
					normal	默认值。动画按正常播放。	测试 »
					reverse	动画反向播放。	测试 »
					alternate	动画在奇数次（1、3、5...）正向播放，在偶数次（2、4、6...）反向播放。	测试 »
					alternate-reverse	动画在奇数次（1、3、5...）反向播放，在偶数次（2、4、6...）正向播放。
					
			animation-play-state	规定动画是否正在运行或暂停。默认是 "running"。
					paused	指定暂停动画	测试 »
					running	指定正在运行的动画
	多列：
		column-count	指定元素应该被分割的列数。
		column-gap	指定列与列之间的间隙
		
		column-rule	所有 column-rule-* 属性的简写
		
		column-rule-color	指定两列间边框的颜色
		
		column-rule-style	指定两列间边框的样式
		
		column-rule-width	指定两列间边框的厚度
		
		column-width	指定列的宽度
		
		columns	column-width 与 column-count 的简写属性。
	=================================================================================	
	用户界面：
		resize
			控制盒子大小改变
			resize: both;
			overflow: auto
			
		box-sizing
			border-box:				可以防止边框与内间距溢出
			
		outline-offset
			outline: 2px solid red;
			outline-offset: 50px;
	=================================================================================

​	

## 弹性盒子

### 概述

弹性盒子是 CSS3 的一种新的布局模式。

CSS3 弹性盒（ Flexible Box 或 flexbox），是一种当页面需要适应不同的屏幕大小以及设备类型时确保元素拥有恰当的行为的布局方式。

引入弹性盒布局模型的目的是提供一种更加有效的方式来对一个容器中的子元素进行排列、对齐和分配空白空间。

### 定义弹性布局

通过display属性来定义弹性布局，默认弹性布局是在一行显示。横向显示。

```
display:flex;
display:inline-flex
```

### 控制方向

横向（默认值)：

从左到右：默认，不需要调整

从右到左：flex-direction: row-reverse;

纵向：

从上到下：flex-direction: column;

从下到上：flex-direction:column-reverse;

### 控制换行

弹性布局默认只有一行，如果需要换行，需要我们手动设置。

```
flex-wrap:wrap;
```

### 分配剩余空间

#### justify-content:

含义：

​	主轴对齐

语法：

``` 
justify-content: flex-start | flex-end | center | space-between | space-around
```

各个值解析：

![1597976139694](C:\Users\l\AppData\Roaming\Typora\typora-user-images\1597976139694.png)

#### align-items 

含义：

​		纵轴(y轴)对齐

语法：

```
align-items: flex-start | flex-end | center | baseline | stretch
```

各个值解析：

- flex-start：弹性盒子元素的侧轴（纵轴）起始位置的边界紧靠住该行的侧轴起始边界。
- flex-end：弹性盒子元素的侧轴（纵轴）起始位置的边界紧靠住该行的侧轴结束边界。
- center：弹性盒子元素在该行的侧轴（纵轴）上居中放置。（如果该行的尺寸小于弹性盒子元素的尺寸，则会向两个方向溢出相同的长度）。
- baseline：如弹性盒子元素的行内轴与侧轴为同一条，则该值与'flex-start'等效。其它情况下，该值将参与基线对齐。
- stretch：如果指定侧轴大小的属性值为'auto'，则其值会使项目的边距盒的尺寸尽可能接近所在行的尺寸，但同时会遵照'min/max-width/height'属性的限制。

#### 	align-content 

含义：

​	设置内容对齐,各个行的对齐

语法：

```
align-content: flex-start | flex-end | center | space-between | space-around | stretch
```

### 排序

#### order

含义：

​	order的值越大，越靠后，反之，越靠前。默认是0.

语法：

```
order:2;
```

### 设置子元素y轴位置

#### align-self

语法：

```
align-self: auto | flex-start | flex-end | center | baseline | stretch
```

取值：

![1597979765285](C:\Users\l\AppData\Roaming\Typora\typora-user-images\1597979765285.png)



### 设置子元素分配空间

#### flex

含义：

​	 `flex` 属性用于指定弹性子元素如何分配空间 

语法：

```js
flex:number;
```

例如：

```
#div1{
flex:1;
}
#div2{
flex:2;
}
#div3{
flex:10;
}
```

效果展示：

![1597980355354](C:\Users\l\AppData\Roaming\Typora\typora-user-images\1597980355354.png)



## 媒体查询

​			

#### 作用

媒体查询可用于检测很多事情，例如：

- viewport(视窗) 的宽度与高度
- 设备的宽度与高度
- 朝向 (智能手机横屏，竖屏) 。
- 分辨率

#### 多媒体查询语法

```
@media not|only mediatype and (expressions) {
    CSS 代码...;
}
```

解释：

- **not:** not是用来排除掉某些特定的设备的，比如 @media not print（非打印设备）。
- **only:** 用来定某种特别的媒体类型。对于支持Media Queries的移动设备来说，如果存在only关键字，移动设备的Web浏览器会忽略only关键字并直接根据后面的表达式应用样式文件。对于不支持Media Queries的设备但能够读取Media Type类型的Web浏览器，遇到only关键字时会忽略这个样式文件。
- **all:** 所有设备，这个应该经常看到

#### 多媒体类型

| all    | 用于所有多媒体类型设备           |
| ------ | -------------------------------- |
| print  | 用于打印机                       |
| screen | 用于电脑屏幕，平板，智能手机等。 |
| speech | 用于屏幕阅读器                   |
| 横屏   | orientation: landscape           |
| 竖屏   | orientation: portrait            |



## Viewport

含义：

​	设置可视化区域的大小

设置：

```
		<meta name="viewport" content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no" />
```



解释：

- width：控制 viewport 的大小，可以指定的一个值，如 600，或者特殊的值，如 device-width 为设备的宽度（单位为缩放为 100% 时的 CSS 的像素）。
- height：和 width 相对应，指定高度。
- initial-scale：初始缩放比例，也即是当页面第一次 load 的时候缩放比例。
- maximum-scale：允许用户缩放到的最大比例。
- minimum-scale：允许用户缩放到的最小比例。
- user-scalable：用户是否可以手动缩放。



​		

# html5

## 什么是 HTML5?

HTML5 是下一代 HTML 标准。

HTML , HTML 4.01的上一个版本诞生于 1999 年。自从那以后，Web 世界已经经历了巨变。

HTML5 仍处于完善之中。然而，大部分现代浏览器已经具备了某些 HTML5 支持。、

## html版本

![1598235215837](C:\Users\l\AppData\Roaming\Typora\typora-user-images\1598235215837.png)



## html声明

![1598235587504](C:\Users\l\AppData\Roaming\Typora\typora-user-images\1598235587504.png)

### HTML5

```
<!DOCTYPE html>
```

### HTML 4.01

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
"http://www.w3.org/TR/html4/loose.dtd">
```

### XHTML 1.0

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

## html新特性

- 用于绘画的 canvas 元素
- 用于媒介回放的 video 和 audio 元素
- 对本地离线存储的更好的支持
- 新的特殊内容元素，比如 article、footer、header、nav、section
- 新的表单控件，比如 calendar、date、time、email、url、search

## 新的标签

### 语义标签：

| <header>     | 定义了文档的头部区域                                     |
| ------------ | -------------------------------------------------------- |
| <aside>      | 定义页面的侧边栏内容。                                   |
| <footer>     | 定义 section 或 document 的页脚。                        |
| <section>    | 定义文档中的段，类似于div                                |
| <article>    | 定义文章或者博客之类的内容                               |
| <details>    | 标签规定了用户可见的或者隐藏的需求的补充细节。           |
| <summary>    | details元素的标题                                        |
| <datalists>  | 表示下拉列表的元素，能够带有搜索的效果                   |
| <time>       | 用来表示时间的                                           |
| <nav>        | 导航链接                                                 |
| <address>    | 表示地址                                                 |
| <figure>     | 表示网页上一个独立的流，通常用来插入图片，图表等内容     |
| <figcaption> | 表示figure的标题部分                                     |
| <mark>       | 表示重点标记的内容                                       |
| <meter>      | 表示度量衡，可以有最大值，最小值，比如用来表示磁盘使用率 |
| <progress>   | 表示进度条，可以有最大值，真实值，最小值。               |

### 表单标签：

#### input新增类型

- color

- date		                                                    日期，包括年月日

- datetime-local                                         日期，包括年月日时分

- month		                                               时间，表示月份
- number                                                    表示数字的，表示这个输入框只能填写数字，可最大值和最小值设置
- range                                                        表示范围的。可以设置最大值，最小值，实际值
- search                                                        表示查询，带x
- time                                                            表示时间的，有小时和分钟
- url                                                             表示网址，自带校验内容的效果
- week                                                         表示时间的，表示一年的第几周
- email	                                                    表示邮件，自带校验效果

#### 表单校验

当输入值的时候，经常我们需要对输入的内容进行校验，看是否正确。在h5当中，为了方便我们对表单输入内容进行校验，开发了一些新的属性给我们使用。

0.设置提示内容

```
<input oninvalid="setCustomValidity('提示内容')"
```



1.非空校验

```
<input require/>
```



2.类型校验

```
邮件类型校验
<input type="email" placeholder="邮件">
```



3.长度校验

```
<input type="text" required="required" placeholder="名字长度不能超过3个字" oninvalid="setCustomValidity('名字的长度只能是2个或者3个,谢谢合作')" maxLength="3" minLength="2">
```



4.范围校验(针对数字的)

```
<input type="number" value="18" min="0" max="100" placeholder="请输入年龄" />
```



5.使用正则表达式进行校验

```
<input type="text" placeholder="手机号" required="required" pattern="^1[3,5,6,7,8,9]\d{9}$" oninvalid="setCustomValidity('请输入正确的手机号码')">
```

## 懒加载

​	含义：

​			网页在加载js文件的时候，是否采用其他的加载方式

​	其他方式：

​			defer：延迟加载。

​							特点：小龙让梨，让别人先加载，别人加载完了，再自己依次加载。

​			async：异步加载

​							特点：没办法保证先后顺序

## 多媒体标签

video

audio

## 画布

### 描述

HTML5 <canvas> 标签用于绘制图像，元素本身并没有绘制能力（它仅仅是图形的容器） - 我们必须使用javascript脚本来完成实际的绘图任务。

### 使用步骤

#### 定义画布

```
<canvas width="500" height="500"></canvas>
```

#### 得到画笔

```
//得到画布
let cvs = document.querySelector("canvas");
//得到画笔
let pen = cvs.getContext("2d");
```

#### 填充矩形

```
//设置颜色
pen.fillStyle="rgba(255,255,25,1)";
//调用填充矩形的函数，就能够画矩形
pen.fillRect(100,150,200,300);
```

#### 画线条

```
//开始画
pen.beginPath();
//设置初始位置
pen.moveTo(100,100);
//下一个点事哪里
pen.lineTo(100,300);
pen.lineTo(200,200);
pen.lineTo(300,300);
pen.lineTo(300,100);
//调用封口的函数
pen.closePath();
//设置画笔的颜色
pen.strokeStyle="#008000";
//设置线条的粗细
pen.lineWidth="10"
//设置连接点的样式    round(圆)    bevel(斜面)		miter(尖角)
pen.lineJoin="round";
//设置线的两头   square(方形)    round（圆形)		butt(默认)
pen.lineCap="square";
//调用画的方法
pen.stroke();
```

#### 填充

```
//设置填充颜色
pen.fillStyle="cyan";
//填充
pen.fill();
```



#### 清除画板

```
pen.clearRect(200,200,50,50);
```



#### 画圆

```
//弧度 = 角度 * π ÷ 180
//   x轴，y轴，半径，起始弧度，结束弧度，方向
pen.arc(200,237,10,0,Math.PI,true);
```

#### 画圆弧

```
pen.beginPath();
pen.moveTo(20,20);           // 创建开始点
pen.arcTo(150,20,150,70,50); // 创建弧
pen.lineTo(150,120);         // 创建垂直线
pen.stroke();   
```

#### 画曲线

主要可以使用贝塞尔曲线来进行绘制

```
https://www.tweenmax.com.cn/tool/bezier/
pen.beginPath()
// pen.moveTo(103.5,307)
// pen.quadraticCurveTo(357.5,36,615.5,294)
pen.moveTo(292.5 ,180)
pen.bezierCurveTo(460.5, 60, 317.5 ,47, 252.5,152);
pen.stroke()
```

#### 设置虚线

```
//设置虚线偏移量
pen.lineDashOffset=10;

//绘制虚线
pen.setLineDash([10,10])
```

#### 绘制文本

```
设置字体
pen.font="120px 幼圆"

设置基线    默认是字在基线的上面，middle居中，top字在基线下面，bottom字在基线上面
pen.textBaseline="bottom";

空心字
pen.strokeText("美酒使我陶醉",100,400);

实心字
pen.fillText("美酒使我陶醉",100,400);

```

#### 绘制图片

```
//加载一张图片
let img = new Image();

//加载哪一张图片
img.src="./timg.jpg";


//等图片加载完毕
img.onload=function(){
//第0个参数，表示图片对象。第一个参数表示x轴位置，第二个参数y轴位置，第三个参数，宽度，第四个参数，高度
pen.drawImage(img,200,200,200,200);
}

//9个参数可以用来切图  
//第一个表示图片对象
//第二，三个表示从哪里开始切
//第四，五个表示切出来的宽高
//第六，七个表示切出来的图片放的位置，x，y轴
//第八，九个表示切出来的图片的缩放
pen.drawImage()
```

#### 变形

##### 平移

```
pen.translate(x,y)
```

##### 旋转

```
以基点为中心，以基点到图形的左上角距离为半径，进行旋转
pen.rotate(弧度)

我们也可以设置基点位置，基点位置默认是左上角0，0，位置
pen.translate(x,y)
```

##### 缩放

```
经过缩放之后，矩形的实际参数为400，60，600，90
pen.scale(2,0.3)
pen.fillStyle="blue";
pen.fillRect(200,200,300,300);
```

#### 状态保存

##### 含义：

​	所谓的状态保存，其实是保存画笔的状态，例如设置了红色，12px，然后临时需要设置18px，黄色，就可以在设置18之前，先保存画笔的状态，等我们使用完了18px，黄色之后，调用回复状态，就可以恢复到12px，红色。

保存状态：

```
保存画笔状态（粗细，颜色等)
pen.save()
```

##### 恢复状态

```
恢复上一次save的粗细颜色等
pen.restore()
```



#### 导出图片

##### 含义：

​		将画布上画好的内容，导出base64码，可以将它应用到img等标签上面去

##### 具体方法:

```
let url = cvs.toDataURL();
document.querySelector("img").src=url;
```

#### 遮罩

```
遮罩图片
-webkit-mask: url(../../img/zz.jpg);
遮罩平铺
-webkit-mask-repeat: no-repeat;
遮罩大小
-webkit-mask-size: 150px 150px;
```

### web存储

#### cookie：

###### 含义：

​		能够保存数据，提供增删改查操作，能够通过<mark>js</mark>来操作，也能够由后台来操作，我们的浏览器会自动选择，将需要发送到后台的cookie数据自行发送过去，不需要手动操作。

###### 操作：

​		下载cookie.js库，建议使用库来操作，因为原生的操作比较麻烦。

​		( https://www.oschina.net/p/cookie-js )



​		增删改查

```
增加数据     (1表示1天后数据才过期)
cookie.set('name', 'jack', 1) 
获取数据	
cookie.get('test')      
删除数据
cookie.remove('uname','upwd')        
```

### 应用缓存	

		含义：
				在本地缓存文件(图片，js，css,文件)
		优点:
			离线浏览 - 用户可在应用离线时使用它们
			速度 - 已缓存资源加载得更快
			减少服务器负载 - 浏览器将只从服务器下载更新过或更改过的资源。
			
		声明离线清单:
			<html manifest="demo.appcache">
			
		 请注意
			manifest 文件需要配置正确的 MIME-type，即 "text/cache-manifest"。必须在 web 服务器上进行配置。
			
		编写离线清单:	
			CACHE MANIFEST	该清单下的内容会在首次下载后缓存
			
			NETWORK:		下面的文件永远需要直接从服务器下载
			login.php
			
			FALLBACK:		如果无法建立因特网连接，则用 "offline.html" 替代 /html5/ 目录中的所有文件：
			/html/ /offline.html
			
		更新缓存:
			用户清空浏览器缓存
			mainfest文件被修改
			由程序来更新应用缓存
			
		最大空间:
			一般浏览器设置每个站点最大缓存大小为5M














