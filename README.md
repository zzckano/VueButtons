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

`ParticleEffect`组件中，由于使用了`slot`，子节点除了可以是一个简单的`button`外，还可以是更复杂的`VNode`。

通过修改`hidden`属性的值，来启动粒子动画。比如用户点击了按钮，程序把`hidden`绑定的变量设为`true`，按钮便会在粒子动画中慢慢消失。

#### 属性参考

- hidden

类型：`Boolean`

默认值：`false`

说明：`ParticleEffect`组件会监控该属性的变化，从而启动相应的特效动画。

- direction

类型：`String`

默认值： `'left'`

说明：可选值包括`'left', 'right', 'top', 'bottom'`。

- particleType

类型：`String`

默认值：`'circle'`

说明：可选值包括`'circle', 'rectangle', 'triangle'`。

- particleStyle

类型：`String`

默认值：`'fill'`

说明：可选值包括`'fill', 'stroke'`。

- particleColor

类型：`String`

默认值：`'#000'`

- duration

类型：`Number`

默认值：`1000`

说明：单位是毫秒。

- easing

类型：`String`或`Array`

默认值：`'easeInOutCubic'`

说明：当绑定的值类型为`String`时，使用预设动画值，以`ease`开头。具体参考[源码](https://gitee.com/pxp/vue-particle-effect/blob/master/src/particle-effect.vue#L114)。

- canvasPadding

类型：`Number`

默认值：`150`

说明：单位是像素。在画布上预留额外的空间来显示动画。

- size

类型：`Number`或`Function`

默认值：`() => Math.floor(Math.random() * 3 + 1)`

说明：单位是像素。

- speed

类型：`Number`或`Function`

默认值：`() => rand(4)`

说明：`rand`函数的定义参见[源码](https://gitee.com/pxp/vue-particle-effect/blob/master/src/particle-effect.vue#L172)。