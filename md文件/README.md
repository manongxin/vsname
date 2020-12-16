#### 一.安装插件
npm install --save redux react-redux@5.1.1 react-router-dom@4.3.1 react-router-redux@5.0.0-alpha.8 redux-thunk redux-logger
或者
cnpm install --save redux react-redux@5.1.1 react-router-dom@4.3.1 react-router-redux@5.0.0-alpha.8 redux-thunk redux-logger

#### 二.创建两个页面
src/pages/main.js
src/pages/about.js

#### 三.删除 文件 App.js  App.css  App.test.js

#### 四.创建路由
src/router.js
```
import React from 'react';
import {Link,Route} from 'react-router-dom';

//引入页面
import main from './pages/main';
import about from './pages/about';

//定义路由
const App = ()=>(
    <div>
        <Link to="/">首页</Link>
        <Link to="/about">关于我们</Link>

        <Route path="/" exact={true} component={main}/>
        <Route path="/about" component={about} />
    </div>
)

export default App;
```


#### 五.创建纯函数
src/modules/index.js
```
//合并状态树
import {combineReducers} from 'redux';
//引入路由的树--路由纯函数
import {routerReducer} from 'react-router-redux';

export default combineReducers({
    routerReducer
})
```
#### 六.创建 store
src/store.js
```
// 引入 redux
//applyMiddleware 允许哪些中间件
//createStore 创建仓库 
import {createStore,applyMiddleware} from 'redux';

//引入路由中间件
import {routerMiddleware} from 'react-router-redux';

// 引入 history
import {createBrowserHistory} from 'history';

//需要引入 纯函数 
import  rootReducer from './modules';

//创建 历史记录
export const history = createBrowserHistory();

//创建并输出仓库
export default createStore(
    rootReducer,
    applyMiddleware(routerMiddleware(history))
);

```

#### 七.修改 src/index.js
```
import React from 'react';
import ReactDOM from 'react-dom';
//引入react-redux
import {Provider} from 'react-redux';
//引入 redux路由插件
import {ConnectedRouter} from 'react-router-redux';

//引入创建好的仓库
import store,{history} from './store';


import App from './router';

import './index.css';

import * as serviceWorker from './serviceWorker';
// <React.StrictMode></React.StrictMode>
ReactDOM.render(
  <React.StrictMode>
  <Provider store={store}>
    <ConnectedRouter history={history}>
    <App />
    </ConnectedRouter>
  </Provider>
  </React.StrictMode>
  ,
  document.getElementById('root')
);

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister();

```