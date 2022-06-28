<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div class="main">
    <DateBtw></DateBtw>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import DateBtw from './components/DateBtw'

export default {
  name: 'App',
  components: {
    //HelloWorld,
    DateBtw,
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
  margin-top: 0px;
  /* border: 10px red solid; */
  background: url("./assets/cloud.jpg") no-repeat;
  display: flex;
  flex-direction: column;
  height: 100vh;
  background-size: auto;
  background-attachment: fixed;
  ;

}
/* .main{
  background: url("./assets/cloud.jpg") no-repeat;
  background-position: center;
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
} */
</style>
