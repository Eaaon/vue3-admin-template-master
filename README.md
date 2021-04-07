# vue3-admin-template-master

简体中文 | [English] (./README-en.md)

> 这是一个极简的 vue admin 管理后台。它只包含了 element-plus UI & axios & iconfont & permission control & lint，这些搭建后台必要的东西。

[线上地址](https://github.com/Eaaon/vue3-admin-template-master.git)

```bash
# 克隆项目
git clone https://github.com/Eaaon/vue3-admin-template-master.git

# 进入项目目录
cd vue3-admin-template-master

# 安装依赖
npm install

# 建议不要直接使用 cnpm 安装以来，会有各种诡异的 bug。可以通过如下操作解决 npm 下载速度慢的问题
npm install --registry=https://registry.npm.taobao.org

# 启动服务
npm run serve
```

浏览器访问 [http://localhost:9521](http://localhost:9521)

## 其它

```bash
# 预览发布环境效果
npm run preview

# 预览发布环境效果 + 静态资源分析
npm run preview -- --report

# 代码格式检查
npm run lint

# 代码格式检查并自动修复
npm run lint -- --fix
```
项目参考来自[vue-admin-template by PanJiaChen](http://panjiachen.github.io/vue-admin-template)

##与[vue-admin-template by PanJiaChen](http://panjiachen.github.io/vue-admin-template)的区别
1. [vue 3.0版本](https://vue3js.cn/docs/zh/)
2. [element-plus](https://element-plus.gitee.io/#/zh-CN)
3. [vue-router 4.0版本](https://next.router.vuejs.org/zh/index.html)
4. [vuex 4.0版本](https://next.vuex.vuejs.org/)
5. [vue-cli 4.0版本](https://cli.vuejs.org/zh/)

##代码改动的地方
1. main.js
```
import { createApp } from 'vue'
import ElementPlus from 'element-plus'
import 'element-plus/lib/theme-chalk/index.css'
import App from './App.vue'
import router from './router'
import store from './store'
import '@/permission' // permission control

import 'normalize.css/normalize.css' // A modern alternative to CSS resets
import '@/styles/index.scss' // global css
import '@/styles/icon.css'

import SvgIcon from '@/components/SvgIcon'// svg component

if (process.env.NODE_ENV === 'production') {
  const { mockXHR } = require('../mock')
  mockXHR()
}

const app = createApp(App)
app.component('SvgIcon', SvgIcon)
app.use(ElementPlus).use(router).use(store).mount('#app')

const req = require.context('@/icons/svg', false, /\.svg$/)
const requireAll = requireContext => requireContext.keys().map(requireContext)
requireAll(req)

```
2. src\layout\components\Sidebar改动比较大是因为路由的问题
3. src\router\index.js
```
import { createRouter, createWebHistory } from 'vue-router'
const router = createRouter({
  history: createWebHistory(process.env.BASE_URL),
  scrollBehavior: () => ({ y: 0 }),
  routes
})
```
4. src\store\index.js
```
import { createStore } from 'vuex'
import getters from './getters'
import app from './modules/app'
import settings from './modules/settings'
import user from './modules/user'

const store = createStore({
  modules: {
    app,
    settings,
    user
  },
  getters
})

export default store

```
5. element-ui的solt="title"改成element-plus的#title
6. 注意 sass安装要用"sass": "1.26.8","sass-loader": "8.0.2",最新版本会报错，估计是不兼容
