# Chrome Extension Boilerplate 项目设计文档

## 项目概述

这是一个基于 React 18 和 Webpack 5 的 Chrome 扩展开发模板，使用 Manifest V3 规范。主要特性包括:

- React 18 + TypeScript 支持
- Webpack 5 + 热重载开发
- Manifest V3 规范
- 多页面组件支持
- SCSS 样式支持

## 目录结构

```
├── src/                      # 源代码目录
│   ├── assets/              # 静态资源
│   │   └── img/            # 图片资源
│   ├── pages/              # 页面组件
│   │   ├── Background/     # 后台脚本
│   │   ├── Content/        # 内容脚本
│   │   ├── Devtools/      # 开发者工具面板
│   │   ├── Newtab/        # 新标签页
│   │   ├── Options/       # 选项页
│   │   ├── Panel/         # 开发者工具子面板
│   │   └── Popup/         # 弹出窗口
│   ├── containers/         # React 容器组件
│   └── manifest.json       # 扩展配置文件
├── utils/                  # 工具脚本
├── webpack.config.js       # Webpack 配置
└── tsconfig.json          # TypeScript 配置
```

## 技术要点

### 1. 扩展页面

- Popup: 点击扩展图标时的弹出窗口
- Options: 扩展的选项配置页面
- Newtab: 新标签页
- Devtools: Chrome 开发者工具面板
- Panel: 开发者工具子面板
- Background: 后台服务脚本
- Content: 注入到页面的内容脚本

### 2. 开发环境

- 支持 TypeScript 开发
- React 18 + React Refresh 热重载
- SCSS 样式处理
- Webpack 5 构建
- ESLint + Prettier 代码规范

### 3. 构建配置

webpack.config.js 主要配置:

- 多入口打包
- TypeScript 和 React 支持
- 资源处理(图片、样式等)
- 开发环境热重载
- 生产环境优化

### 4. 关键文件

- manifest.json: Chrome 扩展配置文件
- webpack.config.js: 构建配置
- tsconfig.json: TypeScript 配置
- utils/: 包含构建和开发服务器脚本

## 开发流程

1. 开发环境启动: `npm start`
2. 生产环境构建: `npm run build`
3. 代码格式化: `npm run prettier`

## 注意事项

1. content_scripts 不支持热重载
2. 开发时需要在 Chrome 扩展管理页面手动加载 build 目录
3. 生产环境构建会自动打包成 zip 文件
4. 支持 secrets 配置用于管理环境变量 