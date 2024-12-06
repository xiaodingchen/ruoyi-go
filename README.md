# 最近在找工作，各位大佬有工作推荐可以联系我，邮箱：1549169735@qq.com
# 若依golang版本实现
## 账密
manager

W5@NSzZTH!

## 配置服务端
服务端代码：https://gitee.com/igolang/imoney.git
### 初始化项目
```shell
gonew gitee.com/igolang/imoney@latest your_module_name your_code_dir
```
### 本地开发
#### 配置数据库
新建数据库，将执行`sql`目录下的SQL文件
#### 配置本地开发环境
```shell
cp -R service/config/dev service/config/local
```
修改数据库、Redis等相关配置

#### 运行
```shell
make run # 本地运行，默认监听3000端口
```

#### 编译
```shell
make build.linux ENV=prod # 编译Linux版本，配置环境为prod
make build.windows ENV=prod # 编译Windows版本，配置环境为prod
make build.docker ENV=prod # 编译为docker镜像，配置环境为prod
```
#### 辅助开发工具
##### 生成数据库对应的结构体model层及dao层

```shell
make gen.dao # 生成代码，文件目录：service/internal/models
```

> 建议将服务端目录设置为`service`

## 配置后台管理前端
下载前端代码：https://gitee.com/igolang/imoney-ui

### 技术栈
1. Vue 3 https://cn.vuejs.org/guide/introduction.html
2. Element Plus https://element-plus.org/zh-CN/

### 前端运行
```bash
# 安装依赖
yarn --registry=https://registry.npmmirror.com

# 启动服务
yarn dev

# 构建测试环境 yarn build:stage
# 构建生产环境 yarn build:prod
```

### 内置功能
1.  用户管理：用户是系统操作者，该功能主要完成系统用户配置。
2.  部门管理：配置系统组织机构（公司、部门、小组），树结构展现支持数据权限。
3.  岗位管理：配置系统用户所属担任职务。
4.  菜单管理：配置系统菜单，操作权限，按钮权限标识等。
5.  角色管理：角色菜单权限分配、设置角色按机构进行数据范围权限划分。
6.  字典管理：对系统中经常使用的一些较为固定的数据进行维护。
7.  参数管理：对系统动态配置常用参数。
8.  通知公告：系统通知公告信息发布维护。
9.  操作日志：系统正常操作日志记录和查询；系统异常信息日志记录和查询。
10. 登录日志：系统登录日志记录查询包含登录异常。
11. 在线用户：当前系统中活跃用户状态监控。
12. 定时任务：在线（添加、修改、删除)任务调度包含执行结果日志。
13. 服务监控：监视当前系统CPU、内存、磁盘、堆栈等相关信息。




> 建议将前端目录设置为 `web`

最终目录如下：
```
.
├── service
│   ├── cmd
│   ├── config
│   ├── internal
│   └── sql
└── web
    ├── bin
    ├── html
    ├── public
    ├── src
    └── vite
```
