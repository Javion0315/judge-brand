<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  created() {
    this.judgeBrand(navigator.userAgent.toLowerCase())
    console.log(navigator.userAgent.toLowerCase())
  },
  methods: {
    judgeBrand(sUserAgent) {
      var isIphone = sUserAgent.match(/iphone/i) == "iphone";
      var isHuawei = sUserAgent.match(/huawei/i) == "huawei";
      var bIsAndroid = sUserAgent.match(/android/i) == "android";
      var isSamsung = sUserAgent.match(/sm-/i) == "sm-";

      if(isIphone) {
        alert('iphone')
        console.log('iphone')
      } else if (bIsAndroid) {
        if(isHuawei) {
          alert('huawei')
          console.log('huawei')
        } else if(isSamsung) {
          alert('samsung')
          console.log('samsung')
        } else {
          alert('android')
          console.log('android')
        }
      } else {
        alert('pc')
        console.log('pc')
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
