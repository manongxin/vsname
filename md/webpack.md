# 概念

webpack是一个打包工具，基于nodejs创造出来。能够帮助我们打包项目中的js，css，html，jpg等一切静态资源文件。



# 安装webpack

```
cnpm i webpack webpack-cli --save-dev

查看版本
npx webpack -v
```



# 初始化目录结构

```
项目
	--package.json
	--src
		--js
		--html
		--css
	--index.html
```



# 打包命令

```
npx webpack a.js b.js c.js
	
	打包完成的路径：
		dist:默认目录			设置目录:		  --output-path    mydist
		main.js:默认文件名		设置文件名:  	--output-filename bundle.js		
```

简化命令

其实就是将命令写入到配置文件中，我们就可以不用每次都写那么长的命令

配置默认是放在根目录下面的webpack.config.js文件当中的。

```javascript
// 引入path模块  $   nodejs自带该模块系统
const path = require('path');
//导出webpack的配置
module.exports = {
  //打包那些东西  --  入口
  entry: './src/index.js',
  //打包完了放哪里 --  出口
  output: {
	//文件名
    filename: 'bundle.js',
	//目录
    path: path.resolve(__dirname, 'dist')   //当前目录/dist
  }
};
```

简化后的打包命令

+ npx webpack

# 配置热部署

其实是帮助我们起了一个服务器

## 安装插件

npm install webpack-dev-server



## 配置插件

在package.json文件中配置启动脚本

```
script:{
	"dev":"webpack-dev-server"  (--contentBase src --port 80 --open --hot)
}
			
配置初始页面所在目录		 --contentBase src

配置端口				  --port 80

配置默认打开				 --open

配置热替换				  --hot

服务器配置也可以配置在webpack.config.js当中
  devServer: {
		port:8081,
		contentBase:'src',
		hot:true
	}
```

## 启动插件

npm run dev

# 打包html

大家发现，我们把js代码打包好了之后，还需要手动在html文件里面去引入，好麻烦！

默认是没有这个功能呢的，(默认只能打包js),要想打包html，需要额外安装插件。

		1.安装插件(包，依赖)
			npm install html-webpack-plugin --save-dev
		
		2.配置插件
			位置：webpack.config.js
			内容：
				const htmlWebpackPlugin = require('html-webpack-plugin');
				plugins:[
					new htmlWebpackPlugin({
						template:'',        //要打包哪个html文件
						filename:'aaa.html'
					})
				]
# css加载器

我们可以配置加载器(loader)，直接打包css代码

```
1.安装加载器（包，依赖)
npm install style-loader css-loader --save-dev

2.配置加载器
位置：webpack.config.js
内容:
module: {
	rules: [
		{ test: /\.css$/, use:['style-loader','css-loader'] }
	]
}
```

# 相对路径处理

我们在加载图片资源的时候，出现相对路径无法正常访问的问题，我们可以通过加载文件加载器来解决

```
1.安装加载器（包，依赖)
npm install file-loader --save-dev

2.配置加载器
位置：webpack.config.js
内容:
module: {
	rules: [
		{ test: /\.jpg|\.png|\.jpeg|\.svg|\.ttf|\.woff$/, use:['file-loader'] }
	]
}
```

# es6中的模块处理

模块处理主要大家要了解导出和导入

导出操作

```
导出多个
export {Person,Doctor}

导出一个
export default Person
```

引入操作

```
引入多个（解构赋值,名称必须对应）
import {Person,Doctor} from './js/Person.js'

引入一个(名称可以随意写)
import p from './js/Person.js'
```









