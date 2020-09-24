<template>
  <div :class="$style.container">
    <h1 :style="{ textAlign: 'center' }">
      Vue Particle Effect Buttons
    </h1>
    <a
      :style="{ position: 'absolute', zIndex: 1000, top: 0, right: 0, border: 0 }"
      href="https://github.com/zzckano/VueButtons"
    >
      <img
        src="https://gitee.com/pxp/vue-particle-effect/widgets/widget_1.svg"
        alt="Fork me on Gitee"
      >
    </a>
    <div :class="$style.blocks">
      <DemoBlock
        v-for="(demo, index) in demos"
        :key="index"
        :background="demo.background"
        :text="demo.text"
        :button-styles="demo.buttonStyles"
        :button-options="demo.buttonOptions"
      />
    </div>
  </div>
</template>

<script>
import DemoBlock from './demo-block'

export default {
  components: {
    DemoBlock,
  },
  data() {
    return {
      demos: [
        {
          background: 'linear-gradient(120deg, #a8edea 0%, #fed6e3 100%)',
          text: 'Send',
          buttonStyles: {
            background: '#121019',
            color: '#fff',
          },
          buttonOptions: {
            particleColor: '#121019',
            duration: 2000,
          },
        },
        {
          background: 'linear-gradient(120deg,#7f54e6,#3F51B5)',
          text: 'Upload',
          buttonStyles: {
            background: '#f3f3f3',
            color: '#3c2e9e',
            padding: '1.8rem 4rem',
          },
          buttonOptions: {
            particleColor: '#f3f3f3',
            particleType: 'triangle',
            easing: 'easeInQuart',
            size: 6,
            particlesAmountCoefficient: 4,
            oscillationCoefficient: 2,
          },
        },
        {
          background: 'linear-gradient(to top, #d299c2 0%, #fef9d7 100%)',
          text: 'Delete',
          buttonStyles: {
            background: '#0e19a2',
            color: '#fff',
            padding: '2rem 4rem',
            borderRadius: 0,
          },
          buttonOptions: {
            particleType: 'rectangle',
            duration: 500,
            easing: 'easeOutQuad',
            particleColor: '#091388',
            direction: 'top',
            size: 8,
          },
        },
        {
          background: 'linear-gradient(to top, #fddb92 0%, #d1fdff 100%)',
          text: 'Submit',
          buttonStyles: {
            background: 'transparent',
            color: '#e85577',
            borderRadius: '15px',
            border: '4px solid #e85577',
          },
          buttonOptions: {
            direction: 'right',
            size: 4,
            speed: 1,
            particleColor: '#e85577',
            particlesAmountCoefficient: 1.5,
            oscillationCoefficient: 1,
          },
        },
        {
          background:
            'linear-gradient(to right, #f78ca0 0%, #f9748f 19%, #fd868c 60%, #fe9a8b 100%)',
          text: 'Refresh',
          buttonStyles: {
            background: '#003ff1',
            color: '#fff',
            padding: '1rem 2rem',
            borderRadius: 0,
          },
          buttonOptions: {
            particleColor: '#003ff1',
            duration: 1300,
            easing: 'easeInExpo',
            size: 3,
            speed: 1,
            particlesAmountCoefficient: 10,
            oscillationCoefficient: 1,
          },
        },
        {
          background: 'linear-gradient(120deg,#9C27B0,#090772)',
          text: 'Bookmark',
          buttonStyles: {
            background: '#f7d337',
            color: '#000000',
            borderRadius: '40px',
          },
          buttonOptions: {
            particleColor: '#f7d337',
            direction: 'bottom',
            duration: 1000,
            easing: 'easeInExpo',
          },
        },
        {
          background: 'linear-gradient(-20deg, #f794a4 0%, #fdd6bd 100%)',
          text: 'Subscribe',
          buttonStyles: {
            background: '#e2405b',
            color: '#e9e9e9',
            padding: '1.8rem 4.5rem',
            borderRadius: 0,
          },
          buttonOptions: {
            particleType: 'rectangle',
            particleStyle: 'stroke',
            size: 15,
            particleColor: '#e87084',
            duration: 600,
            easing: [0.2, 1, 0.7, 1],
            oscillationCoefficient: 5,
            particlesAmountCoefficient: 2,
            direction: 'right',
          },
        },
        {
          background: 'linear-gradient(120deg, #84fab0, #8fd3f4)',
          text: 'Logout',
          buttonStyles: {
            background: 'linear-gradient(to top, #22b9d2 0%, #5389ec 100%)',
            color: '#fff',
            padding: '2rem 4rem',
            borderRadius: '10px',
          },
          buttonOptions: {
            particleType: 'triangle',
            particleStyle: 'stroke',
            size: 5,
            particleColor: 'blue',
            duration: 1400,
            speed: 1.5,
            oscillationCoefficient: 15,
            direction: 'right',
          },
        },
        {
          background: 'linear-gradient(120deg, #d299c2 0%, #fef9d7 100%)',
          text: 'Add to cart',
          buttonStyles: {
            background: '#c13a3a',
            color: '#ffffff',
            padding: '1.5rem 3rem',
            borderRadius: '10px',
          },
          buttonOptions: {
            particleColor: '#c13a3a',
            duration: 500,
            easing: 'easeOutQuad',
            speed: 0.1,
            particlesAmountCoefficient: 10,
            oscillationCoefficient: 80,
          },
        },
        {
          background: 'linear-gradient(120deg, #fddb92 0%, #d1fdff 100%)',
          text: 'Pause',
          buttonStyles: {
            background: '#b1b1b1',
            color: '#fff',
          },
          buttonOptions: {
            direction: 'right',
            size: 4,
            particleColor: '#969696',
            duration: 1200,
            easing: 'easeInCubic',
            particlesAmountCoefficient: 8,
            speed: 0.4,
            oscillationCoefficient: 1,
          },
        },
        {
          background: 'linear-gradient(120deg, #fff1eb 0%, #ace0f9 100%)',
          text: 'Register',
          buttonStyles: {
            background: '#fff',
            color: '#1b81ea',
            padding: '2rem 4.5rem',
            borderRadius: '7px',
          },
          buttonOptions: {
            particleStyle: 'stroke',
            particleColor: '#1b81ea',
            direction: 'bottom',
            duration: 1200,
            easing: 'easeOutSine',
            speed: 0.7,
            oscillationCoefficient: 5,
          },
        },
        {
          background:
            'linear-gradient(to right, #f78ca0 0%, #f9748f 19%, #fd868c 60%, #fe9a8b 100%)',
          text: 'Export',
          buttonStyles: {
            background: '#ff4d73',
            color: '#fff',
            padding: '1.5rem 7rem',
            borderRadius: '40px',
          },
          buttonOptions: {
            particleColor: '#ff4d73',
            particleType: 'triangle',
            easing: 'easeOutSine',
            size: 3,
            duration: 800,
            particlesAmountCoefficient: 7,
            speed: 3,
            oscillationCoefficient: 1,
          },
        },
      ],
    }
  },
}
</script>

<style module>
body {
  padding: 0;
  margin: 0;
  font-family: sans-serif;
}
body::-webkit-scrollbar {
  /*滚动条整体样式*/
  width: 0px;
  /*高宽分别对应横竖滚动条的尺寸*/
  height: 0px;
  /* scrollbar-arrow-color:red; */
}

body::-webkit-scrollbar-thumb {
  /*滚动条里面小方块*/
  border-radius: 15px;
  -webkit-box-shadow: inset 0 0 5px rgba(218, 218, 218, 0.2);
  box-shadow: inset 0 0 5px rgba(218, 218, 218, 0.2);
  background-image: linear-gradient(125deg, #ff8a00, #e52e71);
}

body::-webkit-scrollbar-track {
  /*滚动条里面轨道*/
  border-radius: 0;
  /* background: #1d1d1f; */
  background: #2e2e2e;
  border-left: 1px solid #4f4c57;
}

.container {
  width: 100%;
  min-height: 100vh;
  padding: 48px 0;
  color: #fff;
  background: #000;
}

.blocks {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
