# vuejs

## Vue.js 是什么

 Vue (读音 /vjuː/，类似于 **view**) 是一套用于构建用户界面的**渐进式框架**。与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与[现代化的工具链](https://cn.vuejs.org/v2/guide/single-file-components.html)以及各种[支持类库](https://github.com/vuejs/awesome-vue#libraries--plugins)结合使用时，Vue 也完全能够为复杂的单页应用提供驱动。

## 安装vue

npm安装/cdn安装/离线使用

## 入门案例

```
<div id="app">
			<input v-model="msg" />
			hello {{msg}}	
</div>
<script src="../js/vue.js"></script>
<script>
	new Vue({
		el:"#app",
		data:{
			msg:"李小龙"
		}
	})
</script>
```

## vue实例

### el:

​		el表示当前vue实例控制的视图范围。只有该视图范围的内容才能跟vue实例完成数据交互

### data:

​		表示当前vue实例控制的所有数据，这些数据会完成跟视图的交互。

### 生命周期钩子:

这个东西在项目里面是一个必用的内容，也是考点。但是很简单。所谓生命周期其实就是一个vue实例从出生到销毁的这么一整个过程。钩子函数允许我们再vue实例的生命周期各个过程中插入我们的操作。

```
created(){
			//创建好之后
			console.log("create--",this.msg);
},

mounted:()=>{
			console.log("monted--",this);
			//挂载数据之前
},

beforeDestroy(){
			//销毁vue实例之前
			console.log("beforeDestroy--",this);
},
```

## 安装dev-tools

这是一个vue的调试插件，可以安装在浏览器上面的。



## 模板语法

模板其实就是一种固定的格式，有些东西可以变，有些东西固定不变，例如hello{{name}},也是一种模板，hello不变，name可变。

### 插值表达式{{}}

插值表达式里面可以写javascript表达式。比如执行计算语句，包括三目运算符。

插值表达式里面可以写vue实例data中的比属性名。

插值表达式只能用在标签的内容上，不能用到属性上面去。

插值表达式默认是不支持识别html标签的。如果想要识别标签，要使用v-html指令来进行操作

```
new Vue({

​	data:{

​		name:"jack"

​	}

})
```



## 指令

### v-html

v-html指令可以替代插值表达式，能够识别标签。

```
<p v-html="msg"></p>

data:{
	msg:"<a href="#">百度</a>"
}
```

### v-once:

​	v-once修饰标签，表示这个标签里面的表达式只第一次渲染有效，后期改变无效。

### v-bind:

v-bind修饰属性，表示属性的值可以从vue实例中获取，其实就是将属性值与vue变量进行绑定。这玩意儿可以简写成 :        (  v-bind:    <=>    :)

```
<div id="app">
	<img :src='myurl' />
</div>
data:{
		msg:"万里悲秋常作客",
		myurl:"../../js/day15/wz/phpMyAdmin4.8.5/themes/original/screen.png"
}
```

### v-on:

v-on这个指令是用来绑定事件的。比如绑定点击事件v-on:click="m1" v-on:mouseover="m2",vue里面的函数必须写在vue实例的methods属性里面。v-on:可以简写成@，（  v-on:     <=>    @  )

```
<img :width="mywid" :src='myurl' v-on:click="cg" @mouseover="max"/>

methods:{
		cg(){			
			this.myurl="../../js/day15/wzsigner/help_relation.png"
		},
		max(){
			this.mywid="500"
		}
}
```

### v-model

v-model表示view-model,view表示视图，model表示数据。本质就是表达视图改变，数据改变。

```
注意：其实就是使用v-mode替代value即可
<input v-model="val" />
```

### v-show

v-show只是控制标签的display的可见与不可见，对于频繁切换来讲，用v-show更好。但是对于不频繁切换的，用v-if更好。

```
<div id="app">
		<button @click="lai = ! lai">蓦然回首</button>
		<div v-if="lai"></div>
</div>
```



## 动态参数

能够动态的改变属性的名字。例如写 :[du]="mywid"    ,说明du与mywid都是变量。都绑定了vue里面的data值

```
<img :[du]="mywid" :src='myurl' v-on:click="cg" @mouseover="max"/>
```

## 修饰符

表单修饰符



事件修饰符



## 计算属性

计算属性，可以让复杂的逻辑实现起来更简易，当然他只是一种书写方式而已，并不要求你在哪个地方就一定要用计算属性。其实不要计算属性，我们也完全不影响功能。只是计算属性，为我们负责的逻辑，提供了更简便的实现方式，建议大家去使用。

很多时候，计算属性能做的事情，其实使用方法也完全能够实现，但是计算属性会带缓存效果，如果计算的内容没有变，就不会重新执行计算，而是使用原有缓存的结果，但是如果是使用方法，那么无论原始值是否改变，方法都会重新调用一次。相比较来说，计算属性的性能会优于使用方法来完成。

```
<div id="app">
	{{num1}}
	{{num2}}
</div>

//常规数据
data:{
	num1:10
},
//计算属性
computed:{
	num2(){
		return 20;
	}
}
```

## 侦听器(监听器)

侦听器其实就是监视器，一直监视一个东西(某个变量值)。

计算属性可以存在很多，基本都是耗时比较小的一些计算操作，不会占用特别大的内存开销。允许同时存在多个。

但是侦听器，一般一个侦听器只侦听一个属性，相对来说性能占用会更高。当需要在数据变化时执行异步或开销较大的操作时，这个方式是最有用的 。

```
data:{
			val:"张清水"
},
//watch  看的意思
watch:{
		//侦听器
		val(n,o){
			if(n == "如花"){
				this.val = "变态";
			}
		}
}
```

## 样式操作

其实本质上就是操作class或者style属性的值。只是由于这两个值在实际项目中操作的比较频繁，所以为我们单独封装了操作方法。

### class的值可以是对象。

```
<p :class="myclass"></p>

如果两个都是true，值为redcolor  bluebg    ，两个都是false，就没有值
data:{
	myclass:{redcolor:true,bluebg:true}
}

//最终结果    class="redcolor   bluebg"
```

### class的值可以是数组

```
<p :class="myclass"></p>

data:{
	myclass:["redcolor","bluebg"]
}

//最终结果    class="redcolor   bluebg"




```

另一种形式

```
<p :class="[a,b]"></p>

data:{
	a:"redcolor",
	b:"bluebg"
}

//最终结果    class="redcolor   bluebg"
```

###  style的值

```
<div id="app">
		<div :style="{color:mycolor,fontSize:mysize+'px'}">
				宝剑锋从磨砺出,
				梅花香自苦寒来
		</div>
		//值是一个数组
		<div :style="[mystyle,nistyle]">
				宝剑锋从磨砺出,
				梅花香自苦寒来
		</div>
</div>

data:{
		//在值里面引用变量
		mycolor:"red",
		mysize:30,
		//值是一个对象
		mystyle:{
			color:"blue",
			fontSize:20+"px"
		},
		nistyle:{
			backgroundColor:"pink"
		}
}
```

### 多重值

 这样写只会渲染数组中最后一个被浏览器支持的值。在本例中，如果浏览器支持不带浏览器前缀的 flexbox，那么就只会渲染 `display: flex`。 

```
<div :style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }"></div
```

## if判断

vue为了方便我们做一些逻辑操作，允许我们直接在html中嵌入if判断。

if语句如果为true，内容就会显示出来，否则，页面根本不会渲染该节点(标签).

```
<p v-if="v"></p>
<p v-else-if="v"></p>
<p v-else></p>
```

## v-for

vue为了方便我们操作，为我们封装了循环的语法，允许我们再html中直接使用循环。

```
data表示当前循环的数据
index表示当前循环的下标

<li v-for="(data,index) in datas">
	{{data}}--{{index}}
</li>
```

循环对象

```
data:{
		woman:{
			name:"吴小姐",
			age:52,
			addr:"坂田基地"
		}
	}

<li v-for="value,name,index in woman">
		{{a}}--{{b}}--{{c}}
</li>
```

## template

template是一个模板，是一个标记，允许我们再template标签上书写循环，判断等，但是template不会被渲染到页面上。

## key的管理

vue在渲染html标签的时候，如果重复的内容，就会直接替换某些属性来达到目的，而不是重新替换标签，这样可能会导致该渲染后的标签遗留一些渲染之前的特性或者属性的内容，这样子不是特别的好。如果大家对功能的要求很高，建议使用key来区分不同的标签。

```
<input placeholder="输入用户名" key="1"/>

<input placeholder="输入邮箱账号" key="2"/>
```

## axios

### 特性：

- 从浏览器中创建 [XMLHttpRequests](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)
- 从 node.js 创建 [http](http://nodejs.org/api/http.html) 请求
- 支持 [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) API
- 拦截请求和响应
- 转换请求数据和响应数据
- 取消请求
- 自动转换 JSON 数据
- 客户端支持防御 [XSRF](http://en.wikipedia.org/wiki/Cross-site_request_forgery)

### 安装

```
npm install axios
```



### 用法

```
axios.post(
	url,
	pam
)
.then((data)=>{
	//成功的回调  data.data
})

url表示请求的路径(getAll)，也可以在路径可以带参数(getAll?name=jack&age=18)
pam是表示参数的意思，参数我们既可以写在url里面，也可以用对象的形式，写在pam这个位置，例如
get方式：
{
    params: {
      name: "jack",
      age:18
    }
}
post方式：
{
    name: "jack",
    age:18
}
```

# 修饰符

就是在原本的功能上做一些稍微的改进操作。

修饰符根据修饰的对象不一样，分成几个种类。

## 事件修饰符

专门来修饰各种事件的

```
.once					表示被修饰的事件只执行一次
.stop					阻止事件冒泡
.capture				先捕获冒泡事件，再执行自己的事件
.self					只有你点击了元素本身才执行事件
.prevent				阻止默认事件
.passive				促使滚动事件的默认行为立刻立即执行，而不用等到滚动结束
```

## 按键修饰符

```
.enter
.tab
.delete (捕获“删除”和“退格”键)
.esc
.space
.up
.down
.left
.right
```



## 系统修饰符

```
.ctrl
.alt
.shift
.meta

组合键
.ctrl.67			ctrl+c
```



## 鼠标按钮修饰符

```
.left			点击鼠标左键
.right			点击鼠标右键
.middle			点击鼠标中间键
```

## v-model修饰符

```
.lazy			将input事件改变成change事件，提升用户体验。实际还是要根据实际需求来决定是否使用lazy
.number			将输入的类型转换成数字类型
.trim			将输入的内容的前后空格去掉
```

# 绑定输入框的值

```vue
<form action="http://www.baidu.com" method="GET">
    <input type="text" name="uname" v-model="text" />
    <p></p>
    <textarea rows="10" v-model="textarea"></textarea>
    <p></p>
    <input type="checkbox" name="cks" id="" v-model="car"  value="兰博基尼"/>
    <input type="checkbox" name="cks" id="" v-model="car"  value="法拉利"/>
    <input type="checkbox" name="cks" id="" v-model="car"  value="大众朗逸"/>
    {{car}}
    <p></p>
    <input type="radio" name="a" id="" v-model="sex" value="妖"/>
    <input type="radio" name="a" id="" v-model="sex" value="神" />
    {{sex}}
    <p></p>
    <select v-model="love">
    <option disabled value="">请选择</option>
    <option>小S</option>
    <option>黄渤</option>
    <option>宝强</option>
    </select>
    {{love}}
<input type="submit">
</form>



data:{
    text:"王重阳",
	textarea:"山雨欲来风满楼，我在楼里狮子头",
	ck:false,
	sx:"神",
	car:['兰博基尼'],
	love:[]
}
```

# 组件

## 定义组件

组件其实就是一个对象，这个对象的写法跟vue实例的写法基本差不多，但是不用写el，data不再是属性，而是一个函数，data里面的值需要使用return的形式返回。

```
let Con01 = {
	template:"html内容",
	data(){
		return{
			name:"jack"
		}
	},
	computed:{
	
	},
	methods:{
	
	}
	....
}

```



## 组件的命名

居然有一套自己的规定

第一种命名方式：   使用短横连接   例如

```
命名：my-component-name         引用组件：<my-component-name></mycomponent-name>
```

第二种命名方式：首字母大写  例如

```

命名：MyComponentName			引用组件:<my-compont-name></my-component-name>
```

## 注册组件

### 全局注册

全局注册的组件，所有vue实例都可以去使用

```
Vue.component("Con04",{
	template:`<p>人有悲欢离合，越有阴晴圆缺。</p>`
})
```



### 局部注册

所谓局部注册就是注册给哪个实例，哪个实例就能够使用该组件。

```
let Con01 = {template:'xx'}

new Vue({
	el:"#app",
	components:{
		Con01,Con02
	}
})
```

## 组件传参

组件与组件之间也存在父子(嵌套)关系。例如vue实例使用了a组件，a组件里面又使用了b组件，那么理论上来说a组件只能使用a组件data里面的值，b组件只能使用b组件data里面的值，a不能使用b的值，b也不能使用a的值，那么在实际项目当中，有没有可能a组件要使用vue实例中的值，a组件要使用b组件里面的值，b组件要使用a组件里面的值，呢？答案一定是有可能。那么此时，我们就要学会组件之间如何传递参数。

### 父组件传递给子组件

实现步骤：

1.给子组件新建一个接收参数的属性，使用props来创建

2.在父组件调用子组件的时候，使用第一步创建的属性来传递参数（如果参数值是普通字符串，直接写即可，如果是父组件里面的data值，需要在属性前面添加一个冒号，也可以写v-bind）

3.在子组件中使用第一步定义的属性来使用父组件传来的参数

```
let son = {
	template:`
		<p>{{nam}}</p>			<!-- 张三丰-->
	`,
	props:['nam']
}

let parent = {
	tempate:`
		<son :nam='name'></son>
	`,
	data(){
		return{
			name:"张三丰"
		}
	},
	components:{
		Son
	}
}
```

### 子组件传参给父组件

实现步骤

1.父组件调用子组件的时候，需要创建一个自定义函数(@send) ,然后在自定义函数里面去调用父组件里面的函数，并把值传过去，实现子传父

2.子组件需要向父组件传递参数的时候，使用this.$emit("自定义函数名","参数"),去调用自定义函数.

```
let son = {
	template:`
		<p @click="hand">{{age}}</p>	
	`,
	data(){
		return{
			age:18
		}
	},
	methods:{
		hand(){
			this.age = 21;
			this.$emit("send",this.age);
		}
	}
}

let parent = {
	tempate:`
		<div>
			<son :nam='name' @send="change"></son>
			{{fAge}}
		</div>
	`,
	data(){
		return{
			fAge:0
		}
	},
	methods:{
		change(age){
			this.fAge = age;
		}
	},
	components:{
		Son
	}
}


```

## props

### props的类型

限制值的类型，设置默认值，添加校验，设置是否必须，一旦不符合，立刻跑来一个错儿。

```
 props: {
    // 基础的类型检查 (`null` 和 `undefined` 会通过任何类型验证)
    propA: Number,
    // 多个可能的类型
    propB: [String, Number],
    // 必填的字符串
    propC: {
      type: String,
      required: true
    },
    // 带有默认值的数字
    propD: {
      type: Number,
      default: 100
    },
    // 带有默认值的对象
    propE: {
      type: Object,
      // 对象或数组默认值必须从一个工厂函数获取
      default: function () {
        return { message: 'hello' }
      }
    },
    // 自定义验证函数
    propF: {
      validator: function (value) {
        // 这个值必须匹配下列字符串中的一个
        return ['success', 'warning', 'danger'].indexOf(value) !== -1
      }
    }
```

## v-model

自定义v-model，将v-model使用到组件中，可以方便父子组件的数据同步。v-model使用到组件中，默认会绑定value属性以及input函数，将子组件传递给input的值同步到v-model的值中。我们也可以通过model里面的event来改变input的指向，也可以通过prop来改变对value的指向。

```vue
<div id="app" style="border:3px solid blue;padding:30px;">
		{{hello}}
		<con v-model="hello"></con>  
</div>
<script>
	let Con = {
		template:`
			<h2 style="border:2px solid red;">
				我是儿子，什么样的儿子
				<span @click="$emit('danteng','百善孝为先')">{{hello}}</span>
			</h2>
		`,
		 model: {
		    prop: 'hello',			//将v-model与hello属性进行绑定
			event:"danteng"
		},
		props:{
			hello:{
				type:String,
				default:"hello world"
			}
		}
	}
	new Vue({
		el:"#app",
		data:{
			hello:'你好吗',
			
		},
		components:{
			Con
		}
	})
</script>			
```

## 原生事件绑定组件

### 含义：

​		原生事件默认都是绑定标签的。但是我们这里是想要让原生事件使用在组件上。当我们给组件绑定原生事件的时候，默认是不生效的。要想生效，需要为事件添加native修饰符。但是因为当我们点击组件里面的任何内容都相当于是点击了组件本身，都将会触发事件。如此一来，绑定事件就失去了意义。通常没有人这么做。

​		如果有人这么做，肯定不是为了绑定事件本身而去做。

### 代码：

```
<div id="app">
	<con @click.native="m2"></con>
</div>
```



## sync语法糖

含义：

​		使用sync语法糖，能够更加方便我们子父组件传参。

步骤：

​		1.给子组件绑定事件，调用自定义函数	

```
let Con = {
	template:`
		<p @click="$emit(update:aa,'hello world')">pp</p>
	`
}
```

2.在调用子组件的时候，使用sync语法糖绑定属性值

```
<con :aa.sync="name"></con>  
```

3.将第二步的name绑定到父组件的data中

```
new Vue({
	el:"",
	data:{
		name:""
	}
})
```

# 插槽

## 含义：

插槽允许我们在调用某个组件的时候，传入一些新的组件或者内容给那个组件。其实就是指调用组件的时候，组件中间插入的内容(<con>插槽内容</con>)

## 定义插槽

定义插槽，其实就是通过<slot></slot>标签来定义的。如果没有规定当前插槽的名称，那么他就是叫做默认插槽。插槽是可以有很多个的。

```
<div>
		<p>大江东去，浪淘尽，千古风流人物。    </p>
		<slot name="c1"/>
		<p>乱石穿空，惊涛拍岸，卷起千堆雪。    </p>
		<slot name="c2"/>
		<p>遥想公瑾当年，小乔初嫁了，雄姿英发。</p>
		<slot/>
		<p>故国神游，多情应笑我，早生华发。    </p>
</div>
```



## 插槽的内容

插槽的内容如果没有说明插入到哪个插槽，就是指插入到默认插槽。

#号相当于v-slot:,它是一种缩写形式。vue2.6之后更新的语法。

```
<con>
		<template #c2>
			<p>江山如画，一时多少豪杰。            </p>
		</template>
		<template v-slot:default>
			<p>羽扇纶巾，谈笑间，樯橹灰飞烟灭。    </p>
		</template>
		<template v-slot:c1>
			<p>故垒西边，人道是，三国周郎赤壁。    </p>
		</template>
</con>
```

## 插槽作用域

插槽的内容可以直接使用父组件的data数据。 包括使用爷爷组件的data数据。

把组件插入到插槽里面去，不属于父子关系，是平级的。

如果插槽内容想要使用组件里面的值，需要额外传递出来

```
<con>
		<template #default="slotProps">
				{{msg}}---{{slotProps.user}}
		</template>
</con>
			
let Con = { //  update:aa   --     aa.sync
	    template: `
			<div>
				<p>遥想公瑾当年，小乔初嫁了，雄姿英发。</p>
				<slot v-bind:user="content"/>
				<p>故国神游，多情应笑我，早生华发。    </p>
			</div>
			`,
		data(){
			return{
				content:"我是data的内容，嗯哼"
			}
		}
}			
```



# keep-alive

正常情况下，当我们不适用某一个组件的时候，那个组件就会被销毁，当我们重新启用那个组件的时候，组件就会被重新创建。如果使用keep-alive包裹组件，那么当组件不使用的时候，组件就会被放到缓存里面，当我们再次使用组件的时候，直接从缓存里面还原组件的状态即可，而不需要重新创建(渲染).这样可以防止重复的组件多次被渲染，提高性能。

# 混入

## 含义：

 混入 (mixin) 提供了一种非常灵活的方式，来分发 Vue 组件中的可复用功能。一个混入对象可以包含任意组件选项。当组件使用混入对象时，所有混入对象的选项将被“混合”进入该组件本身的选项。 

## 全局混入

全局混入的内容，所有的vue实例，所有的组件共享内容

```
Vue.mixin({
		data(){
			return{
				msg:"夏雨荷"
			}
		},
		methods:{
			toLowerCase(){
				console.log("字符串转小写");
			}
		},
		mounted() {
			//挂载数据
			console.log("mixin。。。monted");
		}
	})
```

## 局部混入

局部混入的内容，只能当前实例，或者说当前组件可用，子组件也没办法使用。

```
new Vue({
		el:"#app",
		//定义局部混入
		mixins:[
			{
				data(){
					return {
						date:"2020"
					}
				}
			}
		]
	})
```

# 自定义指令

指令是作用在标签上面的，比如循环这个标签(v-for),比如显示这个标签我们用(v-show)，比如为这个标签绑定事件，我们用(v-on),比如设置这个标签的内容我们用(v-html)，等等，vue允许我们自己定义自己的指令去作用在某一个标签上，打到我们自己的目的。

## 命名：

尽量符合命名要求，规范，不用数字等特殊字符开头，避免使用关键字。

注意，组件命名的时候不需要加v-，v-在使用指令的时候直接加上即可。

```
<li v-hello="name"></li>
```

## 位置：

​		肯定是放在标签上

## 注册指令

### 全局注册

全局注册的指令，所有的vue实例都可以用。包括各个组件亦可使用。

```
// 注册一个全局自定义指令 `v-focus`
Vue.directive('focus', {
  // 当被绑定的元素插入到 DOM 中时……
  inserted: function (el) {
    // 聚焦元素
    el.focus()
  }
})
```



### 局部注册

只能当前vue实例，以及他的组件可以使用。

```
new Vue({
		el:"#app",
		directives:{
			"ss":{
				inserted:(el)=>{
					el.style.display="none"
				}
			}
		}
	})
```

## 钩子函数：

指令什么时候执行？指令的执行时间是通过钩子函数来进行控制的。

```
bind:		指令与元素绑定的时候调用，只调用一次
inserted：	元素插入到父元素的时候调用，只调用一次
update：		元素发生变更的时候调用，但是不保证所含子元素全部更新完毕
componentUpdate：元素发生变更的时候调用，但是可以保证是在所有子元素更新完成之后调用
unbind：		指令与元素解绑的时候调用。只调用一次。
```

钩子函数的参数：

```
el：指令所绑定的元素，可以用来直接操作 DOM。类似于js中的this
binding：一个对象，包含以下 property：
	name：指令名，不包括 v- 前缀。
	value：指令的绑定值，例如：v-my-directive="1 + 1" 中，绑定值为 2。
	oldValue：指令绑定的前一个值，仅在 update 和 componentUpdated 钩子中可用。无论值是否改变都可用。
	expression：字符串形式的指令表达式。例如 v-my-directive="1 + 1" 中，表达式为 "1 + 1"。
	arg：传给指令的参数，可选。例如 v-my-directive:foo 中，参数为 "foo"。
	modifiers：一个包含修饰符的对象。例如：v-my-directive.foo.bar 中，修饰符对象为 { foo: true, bar: true }。
vnode：Vue 编译生成的虚拟节点。移步 VNode API 来了解更多详情。
oldVnode：上一个虚拟节点，仅在 update 和 componentUpdated 钩子中可用。
```

# 渲染函数

 Vue 推荐在绝大多数情况下使用模板来创建你的 HTML。然而在一些场景中，你真的需要 JavaScript 的完全编程的能力。这时你可以用**渲染函数**，它比模板更接近编译器。 



# 插件

官方解释

```
插件通常用来为 Vue 添加全局功能。插件的功能范围没有严格的限制——一般有下面几种：
添加全局方法或者 property。如：vue-custom-element
添加全局资源：指令/过滤器/过渡等。如 vue-touch
通过全局混入来添加一些组件选项。如 vue-router
添加 Vue 实例方法，通过把它们添加到 Vue.prototype 上实现。
一个库，提供自己的 API，同时提供上面提到的一个或多个功能。如 vue-router
```

通俗解释

```
自己无法完成的功能，想办法找一个插件来帮助你完成。一些常用的功能，一般都有插件。
```

## 开发插件

```
let 插件名 = {
	install:()=>{
		//全局方法
		//混入
		//指令
		//实例方法
	}
}
```



## 使用插件

```
Vue.use(插件名)
```

# 过滤器

过滤器主要作用是对数据进行过滤，二次处理。主要用在插值表达式，还有一个是v-bind里面 。

## 注册过滤器

过滤器函数有两个参数，第一个参数表示传递过来原本的值，要过滤的那个值，第二个表示自己传过来的参数，这个是可选的。传就有，不传就没有。

### 全局注册：

```
Vue.filter("fix",function(value,b=2){
		return value.toFixed(b);
	})
```

### 局部注册

```
new Vue({
		el:"#app",
		filters:{
			"sex":function(value){
				return value == 1?"男":"女";
			},
			"lai":function(a,b){
				console.log(a,b);
				return "color:red";
			}
		}
	})
```



## 使用过滤器

使用过滤器就是在要过滤的值后面添加一个管道(|)即可.

# 路由

## 介绍

Vue Router 是 [Vue.js](http://cn.vuejs.org/) 官方的路由管理器。它和 Vue.js 的核心深度集成，让构建单页面应用变得易如反掌。包含的功能有：

- 嵌套的路由/视图表
- 模块化的、基于组件的路由配置
- 路由参数、查询、通配符
- 基于 Vue.js 过渡系统的视图过渡效果
- 细粒度的导航控制
- 带有自动激活的 CSS class 的链接
- HTML5 历史模式或 hash 模式，在 IE9 中自动降级
- 自定义的滚动条行为

## 基础路由

引入路由文件

```
<script src="../js/vue.js"></script>
<script src="../js/vue-router.js"></script>
```

定义路由对象

```
let routes = [
			{
				path:"/log",
				component:Login
			},
			{
				path:"/reg",
				component:Register
			}
			
		]
		
//创建路由对象--解释跳转规则
 let router = new VueRouter({
    routes
 })
```

将路由对象与vue进行关联

```
new Vue({
		el:"#app",
		//注册路由
		router
	})
```

提供router-view组件展示窗口

```
<router-view></router-view>
```

使用router-link实现切换

```
<router-link class="login_btn" to="/log">登录</router-link>
```

## 动态路由

所谓动态路由，其实就是指同一个组件渲染不同的数据，从而呈现不同的效果。

动态路由需要涉及路由传参。

传

在router-link里面跳转的时候就需要设置好要传递的参数内容

```
<router-link to="/user/10">走你</router-link>
```

接

在定义路由表的时候，就要定义好用什么名字来接收传过来的参数

```
let routes = [
			{
				path:"/user/:id",
				component:User
			}
			
		]
```

用

我们再组件中，要想使用传递过来的参数，需要使用$route.params对象来接收参数

```
{{$route.params.id}}
```

## 嵌套路由

所谓嵌套路由，是指路由中又有路由，router-view中又有router-view.

```
跳转路由
<router-link to="/dy">电影</router-link>
<router-link to="/dy/aiqing">爱情</router-link>

定义路由
let routes = [
		{
			path:"/wy",
			component:{template:"<h2>我是网页</h2>"}
		},
		
		{
			path:"/dy",
			component:{template:"#tmp"},
			children:[
				{
					//  /dy/aiqing
					path:"aiqing",
					component:{template:"#aiqing"}
				},
				{
					path:"dongzuo",
					component:{template:"#dongzuo"},
					children:[
						{
							path:"/niu",
							component:{template:"<img src='https://dss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=2960460709,1965273981&fm=26&gp=0.jpg'>"}
						}
				]
				},
				
			]
		}
	]
```

## 编程式导航

所谓编程式导航，其实就是不依赖router-link,而是通过代码进行控制。router-link有点儿类似于以前的a标签，编程式导航，类似于js中的location.href="地址".  比如，当我们鼠标放上去要实现跳转，就没办法使用标签的形式，只能用编程式导航。

```
绑定事件
<button @mouseover="gowy">网页</button>

事件编程
new Vue({
	el:"#app",
	methods:{
		gowy(){
			this.$router.push("/wy");
		}
	}
})

```

## 路由传参

第一种：	使用params传参

```
this.$router.push({
					name:"dianying",
					//使用params传参，一定要配合name路由命名一起用，否则无效，不能用path跳转
					params:{
						name:"jack",
						age:"18"
					}
				})
				
获取参数的时候，需要使用$route.params来获取参数
```

第二种：使用query传参

```
this.$router.push({path:"/wy",query:{name:"康康"}})

获取参数的时候，需要使用$route.query来获取参数
```

## 命名视图

含义：

​	同级可以同时存在多个router-view，我们同时展示多个组件。而不是之前那样，只有一个router-view，同一时间只能加载一个组件，多个组件展示需要切换，或者包含关系

```
当我们访问/的时候，名字为a的router-view填充Baidu组件，名字为b的router-view填充Huawei组件，名字为c的router-view，填充Tenxun组件。
{
		path:"/",
		components:{
			a:Baidu,
			b:Huawei,
			c:Tenxun
	}
}
```

## 路由重定向

含义：

​		当我们访问a的时候，给我们重定向到另一个路径b，地址也会显示b的路径，而不是a

```
{
	path:"/abc",
	redirect:"/huawei"
}
```



## 别名

别名相遇为一个组件绑定多个路径名。我们访问那个路劲显示就那个路径名

## 路由组件传参

含义：

​	在组件中使用 `$route` 会使之与其对应路由形成高度耦合，从而使组件只能在某些特定的 URL 上使用，限制了其灵活性。

使用 `props` 将组件和路由解耦：



```
传：
			<router-link to="/huawei/为所欲为">华为</router-link>
收：
			{path:"/huawei/:msg",component:Huawei,alias:"/hw",props:true}
拿:
		let Huawei = {
			props:["msg"],
			template:"<div>我是华为，中华有为,{{msg}}</div>",
		}
```

## history默认

`vue-router` 默认 hash 模式 —— 使用 URL 的 hash 来模拟一个完整的 URL，于是当 URL 改变时，页面不会重新加载。

如果不想要很丑的 hash，我们可以用路由的 **history 模式**，这种模式充分利用 `history.pushState` API 来完成 URL 跳转而无须重新加载页面。

## 导航（路由)守卫

### 全局守卫

守卫所有的路径(path)

```
//设置全局前置守卫---路由---router
	router.beforeEach((to,from,next)=>{
		console.log("to",to);
		console.log("from",from);
		console.log("他来了。。。前置守卫")
		if(!loginType){
			//未登录     loginType的值为false，就进了if，那不就是说明if中写未登录的逻辑
			//去登录不要拦截，去用户中心才拦截
			if(to.path == "/center"){
			//跳登录界面
				next("/login")
				return;
			}
		}
		
		next();
	})
	
	//全局解析守卫--解析完组件的时候运行
	router.beforeResolve((to,from,next)=>{
		console.log("解析守卫");
		next();
	})

	//全局后置钩子
	router.afterEach((to,from)=>{
		// alert('拜拜')
	})
```



### 路由独享守卫

只守卫一个固定的路径(path)

```
{
				path:"/index",component:index,
				//路由独享守卫
				beforeEnter(to,from,next) {
					console.log("路由独享首位，访问了.",to.path)
				}
			}
```

### 组件内的守卫

只守卫某一个固定的组件。

```
let index = {
		template:"<div>我是首页我是首页，嘿嘿</div>",
		//进入组件时的守卫
		beforeRouteEnter:(to,from,next)=>{
			console.log("index.组件进入守卫")
			next();
		},
		//组件更新的守卫
		beforeRouteUpdate:(to,from,next)=>{
			console.log("index。组件更新守卫")//这个守卫主要针对动态路由
		},
		//离开组件的守卫
		beforeRouteLeave:(to,from,next)=>{
			alert("别离开")
			next();
		}
		
	}
```

## 路由元信息

通过路由元信息，来表明每个资源路径是否需要守卫，方便守卫调用。

```
标记：
{path:"/center",component:Center,meta:{requireAuth:true}}

获取标记值：
to是守卫里面自动传递的参数，表示要去往哪里，里面包含地址以及元信息。
to.meta.requireAuth
```

## 过渡效果

含义：

​	目前，我们的路由切换都是顺时的，可以通过transition标签来达到设置过渡的目的。

```scss
1.使用transition包裹router-view，并且设置样式开头
<transition name="vs">
				<router-view></router-view>
			</transition>
2.编写相应的样式效果即可
	.vs-enter-active{transition: all 2s;}
	.vs-enter{opacity: 0;}
	.vs-enter-to{color:deeppink;}	
	.vs-leave-active{transition: all 20s;transform: translateX(-300px);}
	.vs-leave-to{opacity: 0;}	
```

# vueX

## 含义：

​	 Vuex 是一个专为 Vue.js 应用程序开发的**状态管理模式**。它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。Vuex 也集成到 Vue 的官方调试工具 [devtools extension](https://github.com/vuejs/vue-devtools)，提供了诸如零配置的 time-travel 调试、状态快照导入导出等高级调试功能 

​	他的主要作用，其实就是集中管理数据。

## vuex的流程

1.在vue组件里面，通过dispatch来触发actions提交修改数据的操作。

2.然后再通过actions的commit来触发mutations来修改数据。

3.mutations接收到commit的请求，就会自动通过Mutate来修改state（数据中心里面的数据状态）里的数据。

4.最后由store触发每一个调用它的组件的更新

<img src="./mdimg/vuex.png" width="500"/>

## 入门

```
引入vuex
<script src="../js/vuex.js"></script>

创建仓库
let store = new Vuex.store({
	state:{
		number:10
	},
	mutations:{
		changeNumber(){
			this.state.number+=2;
		}
	}
})

//注册仓库
new Vue({
	el:"",
	store
})

//访问仓库中的值
{{$store.state.number}}

修改仓库中的状态值   --   所有的更新都集中到mutations中去进行，不能直接改。
@click="$store.commit('changeNumber')"
```

## state

state表示store保存的数据。官方为我们提供了mapState帮助我们简化state中的数据的获取流程。

```
引入mapState
let mapState = Vuex.mapState;

通过计算属性在需要用到store值的组件中使用mapState获取值
mapState值为对象
computed:mapState({
	"n":"number",			//state.number
	"c":"count"
})

mapState值为数组  --  前提是number，count必须与state中的值的名字保持一致，否则无效
computed:mapState(["number","count"])

mapState值也可以为函数(省略)

mapState值结合解构一起使用，可以写多个computed值。
computed:{
	...mapState(["number","count"]),
	name(){return "jack";}
}
```

## Getter

比如有一些学生数据，我们希望获取1所有学生数据2学生总人数3所有男生4所有成年女生。我们可以使用getters返回数据，跟在state中的数据差不多，都可以通过store进行访问.只是说，我们一般认为，state中是基数据，getters中是基于state计算出来的数据。但是都可以用。

如何在getters中定义返回数据

```
{
	state:{},
	getters:{
		name:(s,g)=>{
//s表示仓库本身，通过s我们可以访问state中的数据局，g表示getters本身，通过g我们可以访问getters中的其他数据
			return "小王";
		},
		//还可以进行传参
		person:(s,g)=>(canshu)=>{
			console.log(canshu);  //可以使用参数
			return "值";
		}
	}

}
```

如何获取getters里面的数据

```
直接获取
{{$store.getters.name}}

通过计算属性，结合mapGetters获取数据
需要先获取mapGetters		（let mapGetters = Vuex.mapGetters;）
computed:{
	...mapGetters({
		"n":"name",					//{{n}}
		"p":"person"				//{{p}}
	}),
	...mapGetters(["name","person"]),		//{{name}}  {{person}}
	suibian(){								//
		return this.$store.getters.person("小月");
	}
}

若需要传参给getters
{{$store.getters.person('小月')}}
```

## Mutation

mutation的主要作用就是可以修改state数据，而且vuex建议我们只能用mutation来更改数据。因为我们的其他插件都是监控mutation的。

所有的修改都需要通过mutations进行修改.

```
//定义mutations，在store里面定义的。

const CHANGE_ADDR = "cgAddr";
const CHANGE_BTFUL = "cgBtful";

let mapMutations = Vuex.mapMutations;
	
	mutations:{
			changeState(s,m){
				s.name=m;
			},
			[CHANGE_ADDR](s,m){
				s.addr=m;
			},
			[CHANGE_BTFUL](s,m){
				s.btful=m;
			}
		}
		
//在methods里面调用mutations
methods:{
	changeState(){
		this.$store.commit("changeState",this.m);
	},
	...mapMutations([CHANGE_ADDR,CHANGE_BTFUL])
}

//在组件中触发methods
@click="changeState"
@click="cgAddr('xx')"
```

## action

我们再提交更新的时候，既可以commit提交给mutations，也可以dispatch给action，让action去commit给mutations。其实，我们一般都是在action中进行一些逻辑操作，或者异步操作。

```
定义action  --action需要提交给mutation
actions:{
			initBtf(s){
				//异步操作
				axios.get("./data.json")
				.then(resp=>{
					s.commit(CHANGE_BTFUL,resp.data);
				})
			}
		}

在method中调用action--结合mapActions一起使用
methods:{
			...mapActions(["initBtf"])
		}
		
在事件中调用method
@click="initBtf()"
```







