# 项目介绍

集成 [chili3d](https://github.com/xiangechen/chili3d) 项目，将 `chili3d` 的核心库打包成 libs 库模式，方便在 `vue` 中使用，项目使用 `vue^2.7`

# 拉取项目

```shell
git clone https://github.com/kaijia323/chili3d-vue.git
```

# 依赖安装

## chili3d 项目依赖

```shell
npm i --prefix ./chili3d --verbose
```

## vue 项目依赖

```shell
npm i --verbose
```

# 打包生成 chili3d-libs 库

```shell
npm run build:chili3d
```

打包成功后的依赖 [public/chili3d-libs](./public/chili3d-libs)

# chili3d 项目改动逻辑

1. chili3d 改动打包逻辑，新增 `rspack` 的库配置文件 [rspack.libs.config.js](./chili3d/rspack.libs.config.js)
2. 新增打包命令 `build:libs`

# 运行

```shell
npm run dev
```

# chili3d 样式初始化

[child3d.css](./src/assets/chili3d.css)

# vue 项目使用 chili3d 库

目前挂在没有走 vue 的逻辑，后续可以考虑处理一下

```vue
# App.vue
<script setup>
// prettier-ignore
new window.Chili3d.AppBuilder()
    .useIndexedDB()
    .useWasmOcc()
    .useThree()
    .useUI()
    .build()
    .then(x => {
        // document.body.removeChild(loading)
        console.log('chili3d 加载完成')
    })
    .catch((err) => {
        console.error(err);
    });
</script>

<template>
  <div id="app"></div>
</template>
```
