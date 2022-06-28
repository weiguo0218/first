<template>
  <div class = "first">Hey you</div>
  <date-handler></date-handler>
</template>

<script>
import DateHandler from './DateHandler.vue'
export default {
  name: 'HelloWorld',
  components:{
    DateHandler
  }
}
  </script>

<style>
.first{
  color: #000;
  font-size: 400%;
}
#building{
  background:url("../img/cloud.jpg");
  width:100%;
  height:100%;
  position:fixed;
  background-size:100% 100%;
}

</style>