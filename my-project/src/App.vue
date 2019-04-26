<template>
  <div id="app">
    <img src="./assets/logo.png">
<!--    <router-view/>-->
    <div>
      <div>

        <button @click="goBack">后退</button>
        <button @click="go">前进</button>
        <button @click="goHome">返回首页</button>
      </div>
      <p>导航：
      <router-link to="/">首页</router-link>  |
      <router-link to="/hi">Hi</router-link>  |
<!--      <router-link >valueString</router-link>-->
      <router-link :to="{name:'Hi1',params:{username:'fxf',id:'8'}}">Hi页面1</router-link>  |
      <router-link to="/hi/hi2">Hi页面2</router-link>  |
      <router-link to="/params/198/taiji website is very good">params</router-link>  |
      </p>
    </div>
    <router-view></router-view>
    <router-view name="left" style="float:left;width: 50%;height:300px;background-color: #ccc"></router-view>
    <router-view name="right" style="float:left;width: 50%;height:300px;background-color: #c6c"></router-view>

  </div>
</template>

<script>
export default {
  name: 'App',
  methods:{
    goBack(){
      this.$router.go(-1);
    },
    go(){
      this.$router.go(1);
    },
    goHome(){
      this.$router.push('/');
    }

  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
