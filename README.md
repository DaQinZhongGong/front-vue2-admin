#### END-SB2-ADMIN 和 FRONT-VUE2-ADMIN 项目源码

|        | 后端源码                                            | 前端源码                                               |
|--------|-------------------------------------------------|----------------------------------------------------|
| github | https://github.com/DaQinZhongGong/end-sb2-admin | https://github.com/DaQinZhongGong/front-vue2-admin |
| 码云     | https://gitee.com/DaQinZhongGong/end-sb2-admin  | https://gitee.com/DaQinZhongGong/front-vue2-admin  |

<h1 style="text-align: center"> END-SB2-ADMIN </h1>

#### END-SB2-ADMIN 项目简介

[END-SB2-ADMIN](https://github.com/DaQinZhongGong/end-sb2-admin) 基于 Spring Boot
2.x、Jpa、Mybatis-Plus、 Spring Security、Redis 等后端技术栈，实现的后台管理系统！

#### END-SB2-ADMIN 系统功能

- 用户管理：提供用户的相关配置
- 角色管理：对权限与菜单进行分配，可根据部门设置角色的数据权限
- 菜单管理：已实现菜单动态路由，后端可配置化，支持多级菜单
- 部门管理：可配置系统组织架构，树形表格展示
- 岗位管理：配置各个部门的职位
- 字典管理：可维护常用一些固定的数据，如：状态，性别等
- 系统日志：记录用户操作日志与异常日志，方便开发人员定位排错
- SQL监控：采用druid 监控数据库访问性能
- 定时任务：整合Quartz做定时任务，加入任务日志，任务运行情况一目了然
- 代码生成：高灵活度生成前后端代码，减少大量重复的工作任务
- 邮件工具：配合富文本，发送html格式的邮件
- 七牛云存储：可同步七牛云存储的数据到系统，无需登录七牛云直接操作云数据
- 支付宝支付：整合了支付宝支付
- 服务监控：监控服务器的负载情况
- 运维管理：一键部署你的应用

#### END-SB2-ADMIN 项目结构

项目采用按功能分模块的开发方式，结构如下

- `sb2-admin-jpa` 是 END-SB2-ADMIN 的 Jpa 版本
  - `sb2-admin-jpa-common` 为系统的公共模块，各种工具类，公共配置存在该模块
    - annotation 为系统自定义注解
    - aspect 自定义注解的切面
    - base 提供了Entity、DTO基类和mapstruct的通用mapper
    - config 自定义权限实现、redis配置、swagger配置、Rsa配置等
    - exception 项目统一异常的处理
    - utils 系统通用工具类
  - `sb2-admin-jpa-generator` 为系统的前后端代码生成模块，支持生成前后端CRUD代码
  - `sb2-admin-jpa-logging` 为系统的日志模块，其他模块如果需要记录日志需要引入该模块
  - `sb2-admin-jpa-sql` 为 END-SB2-ADMIN 的 Jpa 版本对应的基础表结构与基础数据 sql 脚本
  - `sb2-admin-jpa-system` 为系统核心模块也是项目入口模块，也是最终需要打包部署的模块
    - config 配置跨域与静态资源，与数据权限
      - thread 线程池相关
    - modules 系统相关模块(登录授权、系统监控、定时任务、运维管理等)
  - `sb2-admin-jpa-tools` 为第三方工具模块，包含：邮件、七牛云存储、本地存储、支付宝等

- `sb2-admin-mp` 是 END-SB2-ADMIN 的 Mybatis-Plus 版本
  - `sb2-admin-mp-common` 为系统的公共模块，各种工具类，公共配置存在该模块
    - annotation 为系统自定义注解
    - aspect 自定义注解的切面
    - base 提供了Entity、DTO基类和mapstruct的通用mapper
    - config 自定义权限实现、redis配置、swagger配置、Rsa配置等
    - exception 项目统一异常的处理
    - utils 系统通用工具类
  - `sb2-admin-mp-generator` 为系统的前后端代码生成模块，支持生成前后端CRUD代码
  - `sb2-admin-mp-logging` 为系统的日志模块，其他模块如果需要记录日志需要引入该模块
  - `sb2-admin-mp-sql`  为 END-SB2-ADMIN 的 Mybatis-Plus 版本对应的基础表结构与基础数据 sql 脚本
  - `sb2-admin-mp-system` 为系统核心模块也是项目入口模块，也是最终需要打包部署的模块
    - config 配置跨域与静态资源，与数据权限
      - thread 线程池相关
    - modules 系统相关模块(登录授权、系统监控、定时任务、运维管理等)
  - `sb2-admin-mp-tools` 为第三方工具模块，包含：邮件、七牛云存储、本地存储、支付宝等

<h1 style="text-align: center"> FRONT-VUE2-ADMIN </h1>

#### FRONT-VUE2-ADMIN 项目简介

[FRONT-VUE2-ADMIN](https://github.com/DaQinZhongGong/front-vue2-admin) 基于
ES2015+、vue、vuex、vue-router 、vue-cli 、axios、mock.js 和 element-ui 等前端技术栈实现，是 end-sb2-admin
后端代码仓库对应对的前端代码仓库！

#### Build Setup

** node 版本[FRONT-VUE2-ADMIN 项目必须使用这个推荐版本]：v16.20.2 **
** npm 版本[FRONT-VUE2-ADMIN 项目必须使用这个推荐版本]：v8.19.4 **
** Python 版本[FRONT-VUE2-ADMIN 项目必须使用这个推荐版本]：v2.7.18 **

``` bash
# 配置镜像加速

# 首先配置淘宝的镜像源
npm config set registry https://registry.npmmirror.com
# 然后在 ~/.npmrc 加入下面内容
sass_binary_site=https://registry.npmmirror.com/mirrors/node-sass/
# windows系统的 .npmrc 文件位于：C:\Users\[你的账户名称]\.npmrc
# linux系统的 .npmrc 文件位于：直接使用 vim ~/.npmrc

# 安装依赖
npm install --registry=https://registry.npmmirror.com

# 启动服务
npm run dev

## 使用 ESLint 统一项目的编码风格
npm run lint

# 构建生产环境部署 dist 包
npm run build:prod

```

#### FRONT-VUE2-ADMIN 项目在安装依赖的时候会出现 node-sass 无法安装的问题

解决方案：

```
1. 首先，安装 Python [FRONT-VUE2-ADMIN 项目必须使用这个推荐版本]：v2.7.18 对应版本的版本，在安装编译 sass 时会用到
2. 然后，单独安装：npm install --unsafe-perm node-sass 
3. 其次，直接使用：npm install --unsafe-perm

```




