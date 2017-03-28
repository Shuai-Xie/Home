# :apple: Our Home :heart:
## Setup
无论是开发还是部署，都要先安装 Nodejs (v7.6.0 以上版本)和 MongoDB。

### 开发配置
``` bash
# 假定已安装 Nodejs v7.6.0+ 和 MongoDB

# clone 项目并设置
$ git clone git@github.com:CSU-Apple-Lab/Home.git
$ npm i
$ cd Home/init
$ cp config.example.js config.js
$ vim config.js                              # 编辑配置文件，包含监听端口，MongoDB 端口及其用户验证等
$ cd ..

# 调试运行
$ NODE_ENV=development node index.js
```

### 部署配置
``` bash
# 假定已安装 Nodejs v7.6.0+ 和 MongoDB

# 安装 pm2
$ sudo npm i -g pm2

# clone 项目并设置
$ git clone https://github.com/CSU-Apple-Lab/Home.git
$ npm i --production
$ cd Home/init
$ cp config.example.js config.js
$ vim config.js                                     # 编辑配置文件，包含监听端口，MongoDB 端口及其用户验证等
$ cd ..

# 配置部署配置(可选)
$ vim labHome.yml

# Caddy 反向代理配置与部署(可选)
# 假定已安装 Caddy 并已设置监听权限
$ cp Caddyfile /home/www/caddy
$ vim /home/www/caddy/Caddyfile                     # 修改端口、日志路径等
$ vim caddy.yml                                     # 修改 Caddy 路径等
$ pm2 start caddy.yml

# 部署
$ pm2 start lab-home.yml
```

## TODO
### 前端
* [ ] 修复表单
* [ ] 修复路由

### 后端
* [x] 解决 hbs 渲染问题
* [ ] 与前端对接 API 参数
* [ ] 添加日志模块
* [ ] 完善插入新数据前的查重与异常处理，将错误类型反馈到前端
* [ ] 添加渲染 400, 404, 500 等页面的中间件

## Contributors
[![Equim](https://avatars3.githubusercontent.com/u/17795845?v=3&s=100 "Equim")](https://github.com/Equim-chan)
[![Zijin Xiao](https://avatars3.githubusercontent.com/u/4846135?v=3&s=100 "Zijin Xiao")](https://github.com/jxpxxzj)
[![Bugzhang](https://avatars2.githubusercontent.com/u/9525158?v=3&s=100 "Bugzhang")](https://github.com/rhythm1995)

## Powered by
[![CSU Apple Lab](https://avatars1.githubusercontent.com/u/23062358?v=3&s=100 "CSU Apple Lab")](https://github.com/CSU-Apple-Lab)
