
#目录
- [目录结构](#目录结构)
- [安装依赖](#安装依赖)
- [代码规范](#代码规范)
- [功能实现](#功能与路由设计)

I think I need a blog

## 目录结构

### models
存放操作数据库的文件
### public
存放静态文件，如样式、图片
### routes
存放路由文件
### views
存放模块文件
### index.js
程序主文件
### package.json
项目信息

## 安装依赖
```
npm i config-lite connect-flash connect-mongo ejs express express-session marked moment mongolass objectid-to-timestamp sha1 winston express-winston --save

npm i https://github.com:utatti/express-formidable.git --save
```
### 依赖说明
1. express: web框架
2. express-session: session 中间件
3. connect-mongo: 将 session 存储于 mongodb
4. connect-flash: 页面通知的中间件，基于session实现
5. ejs: 模板
6. express-formidable: 接收表单及文件上传的中间件
7. config-lite: 读取配置文件
8. marked: Markdown解析
9. moment: 时间格式化
10. mogolass: MongoDB驱动
11. objectid-to-timestamp:根据objectId生成时间戳
12. sha1: sha1加密
13. Winston: 日志
14. express-winston: express 的winston 日志中间件

## 代码规范
### ESLint
Standard 规范,主要特点是不加分号
### EditorConfig
可以在vscode扩展里面找，或者 ctrl+shift+P 然后输入 ext install EditorConfig，安装后重启vscode（点击重新加载）

## 功能与路由设计

1. 注册
  1. 注册页 GET  /signup
  2. 注册  POST /signup
2. 登陆
  1. 登陆页 GET /signin
  2. 登陆  POST /signin
3. 登出  GET .signout
4. 查看文章
  1. 主页  GET /home
  2. 个人主页 GET /home?author=xxx   以下待定
  3. 查看文章 GET /home/:id
5. 发表文章
  1. 页面  GET /home/create
  2. 发表 POST /home/create
6. 修改文章
  1. 页面  GET /home/:id/edit
  2. 修改 POST /home/:id/edit
7. 删除文章 GET /home/:id/remove
8. 留言
  1. 页面  GET /comments
  2. 创建 POST /comments
  3. 删除  GET /comments/:id/remove

### 后续可添加功能
1. 自动获取GitHub账号登陆
