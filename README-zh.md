# vue-admin-template

> 这是一个极简的 vue admin 管理后台。它只包含了 element-plus UI & axios & iconfont & permission control & lint，这些搭建后台必要的东西。

[线上地址](https://github.com/Eaaon/vue3-admin-template-master.git)

```bash
# 克隆项目
git clone https://github.com/Eaaon/vue3-admin-template-master.git

# 进入项目目录
cd vue3-admin-template

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
