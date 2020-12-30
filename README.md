后端工程启动
项目结构
ace-security

ace-api--------------跨服务调用通用dto数据对象

ace-modules--------------公共服务模块（基础系统和JWT鉴权、搜索、OSS）

ace-dev-base---------------通用脚手架（基础jwtsdk、开发常用工具类）

ace-gate-----------------网关负载中心

ace-infrastructure--------------运维中心（监控、链路、naco注册中心、sentinel熔断流控）
环境须知!
mysql一个，redis一个，sentiel一个，nacos注册中心一个
jdk1.8
IDE插件一个，lombok插件，具体百度即可
搭建
须知
因为Cloud-Platform是一个前后端分离的项目，所以后端的服务必须先启动，在后端服务启动完成后，再启动前端的工程。

最多人问：代码有漏
下载完后端代码后，记得先安装lombok插件，否则你的IDE会报代码缺失。

运行步骤
先启动redis、redis、mysql以及nacos注册中心

运行数据库脚本：依次运行数据库：ace-modules/ace-admin/db/init.sql

依次配置修改：ace-admin/src/main/resources/application.yml、ace-gate/src/main/resources/application.yml

按顺序运行main类：AdminBootstrap（ace-admin）、GatewayServerBootstrap（ace-gate）

UI工程启动[Cloud-Admin-UI-V2]点击打开
环境搭建(node 版本 > 8)
node 版本：v9.4.0
npm 版本：6.10.2
依赖下载慢
~ nrm -V
1.0.2
➜  ~ nrm ls
npm ---- https://registry.npmjs.org/
cnpm --- http://r.cnpmjs.org/
* taobao - https://registry.npm.taobao.org/
  nj ----- https://registry.nodejitsu.com/
  rednpm - http://registry.mirror.cqupt.edu.cn/
  npmMirror  https://skimdb.npmjs.com/registry/
  edunpm - http://registry.enpmjs.org/
  开发（在UI目录下）

# 安装依赖
npm install

# 本地开发 开启服务
npm run dev
浏览器访问 http://localhost:8080/

发布
# 构建生成环境
npm run build:prod
