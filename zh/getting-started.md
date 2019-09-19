# 开始使用

ng-matero 是基于 Angular Material 组件库开发的项目，所以你需要了解 TypeScript 及 Sass 的基础知识。

## 安装

使用 CLI 初始化项目是最便捷的方式，通过初始化选项可以定制主题样式等。详情查看 [添加项目](schematics/project-init.md)

```bash
$ ng new <project-name>
$ cd <project-name>
$ ng add ng-matero
```

除了 CLI 安装方式之外，也可以克隆 starter 仓库，不过 starter 只有侧边栏一种布局样式。

```bash
$ git clone --depth=1 git@github.com:ng-matero/starter.git <project-name>
$ cd <project-name>
$ npm install
```

## 本地开发

建议使用 hmr 运行程序，不要使用 `npm start` 或者 `ng serve`

```bash
$ npm run hmr
```

克隆完整仓库

```bash
$ git clone git@github.com:ng-matero/ng-matero.git
$ cd ng-matero
$ npm install
$ npm run hmr
```

打开浏览器访问 `http://localhost:4200/`

![](screenshot.jpg)

## 项目目录

```plain
├── src
│   ├── app
│   │   ├── core                                # 核心文件
│   │   │   ├── interceptors                    # HTTP 拦截器
│   │   │   │   └── default.interceptor.ts      
│   │   │   ├── services                        # 服务
│   │   │   │   ├── settings.service.ts         # 页面布局配置
│   │   │   │   ├── menu.service.ts             # 菜单配置
│   │   │   │   └── startup.service.ts          # 初始化项目配置
│   │   │   │── core.module.ts                  # 核心模块
│   │   │   │── **
│   │   │   └── settings.ts                     # 布局配置选项
│   │   ├── routes                              # 业务文件
│   │   │   ├── **                              
│   │   │   ├── routes-routing.module.ts        # 业务路由注册口
│   │   │   └── routes.module.ts                # 业务路由模块
│   │   ├── shared                              # 共享文件
│   │   │   |—— **
│   │   │   └── shared.module.ts                # 共享模块
│   │   ├── theme                               # 主题文件
│   │   │   ├── admin-layout                    # Admin 布局
│   │   │   ├── auth-layout                     # 登陆注册布局
│   │   |   └── theme.module.ts                 # 主题模块
│   │   ├── app.component.ts                    # 根组件
│   │   └── app.module.ts                       # 根模块
│   │   └── material.module.ts                  # Material 组件模块
│   ├── assets                                  # 本地静态资源
│   ├── environments                            # 环境变量配置
│   ├── styles                                  # 样式目录
│   │   ├── functions                           # 函数
│   │   ├── helpers                             # 工具类
│   │   ├── mixins                              # mixin
│   │   ├── plugins                             # 第三方库样式
│   │   ├── theme                               # 主题核心样式
│   │   ├── widgets                             # 公用组件
│   │   ├── **
│   │   └── app.scss                            # 主题样式入口文件
└── └── style.scss                              # 样式主入口文件
```

目录结构遵循 Angular 风格指南，同时也是为了方便 CLI 添加业务模块，后期可能还有微调。

## 项目运行

项目运行后默认执行 `startup.service`，项目启动前的一些关键信息，比如菜单、用户信息等，都可以写在 `startup.service` 中。
