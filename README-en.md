# vue3-admin-template-master


> A minimal vue admin template with Element-plus UI & axios & iconfont & permission control & lint

## Project setup
```
# clone the project
git clone https://github.com/Eaaon/vue3-admin-template-master.git

# enter the project directory
cd vue3-admin-template

# install dependency
npm install

### Compiles and hot-reloads for development
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

reference from[vue-admin-template by PanJiaChen](http://panjiachen.github.io/vue-admin-template)

##diffenert from [vue-admin-template by PanJiaChen](http://panjiachen.github.io/vue-admin-template)
1. [vue 3.0](https://vue3js.cn/docs/zh/)
2. [element-plus](https://element-plus.gitee.io/#/zh-CN)
3. [vue-router 4.0](https://next.router.vuejs.org/zh/index.html)
4. [vuex 4.0](https://next.vuex.vuejs.org/)
5. [vue-cli 4.0](https://cli.vuejs.org/zh/)

##code changed
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
2. src\layout\components\Sidebar
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
5. solt="title"(element-ui)changed to #title(element-plus)
6. use sass instal "sass": "1.26.8","sass-loader": "8.0.2"
