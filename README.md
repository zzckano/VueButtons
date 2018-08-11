# vue-particle-effect ([demo](https://pxp.gitee.io/))

#### 项目介绍

Vue 版本的粒子效果。[react-particle-effect-button](https://github.com/transitive-bullshit/react-particle-effect-button) 的 Vue 移植。除 Vue 框架外零依赖。

#### 软件架构

核心文件只有一个： [particle-effect.vue](https://gitee.com/pxp/vue-particle-effect/blob/master/src/particle-effect.vue)


#### 安装教程

将 `particle-effect.vue` 复制到你的项目目录中，自行修改适配。

下载项目所有文件后，如果想在本地调试代码，请执行以下命令：

```bash
yarn install
yarn dev
```

#### 使用说明

```vue
<script>
import ParticleEffect from './particle-effect'

export default {
  data() {
    return {
      effectHidden: false,
    }
  },
  methods: {
    onBegin() {
      console.log('begin event')
    },
    onComplete() {
      console.log('complete event')
    },
  },
}
</script>

<template>
  <ParticleEffect
    :hidden="effectHidden"
    direction="left"
    particle-type="circle"
    particle-style="fill"
    particle-color="#000"
    :duration="1000"
    easing="easeInOutCubic"
    :canvas-padding="150"
    :size="4"
    :speed="2"
    :particles-amount-coefficient="3"
    :oscillation-coefficient="20"
    @begin="onBegin"
    @complete="onComplete"
  >
    BUTTON CONTENT GOES HERE
  </ParticleEffect>
</template>
```

`ParticleEffect`组件中，由于使用了`slot`，子节点除了可以是一个简单的`button`外，还可以更复杂的`VNode`。