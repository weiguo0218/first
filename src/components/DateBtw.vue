<template>
<div class = "outter">
  <div class = "hey">
    <h1>Hey you</h1>
    <h2>加个日期和时间</h2>
    <h2>柏xx项目到期</h2>
  </div>
  <button v-on:click="handleDisplayClick">日期计算器</button>
  <div class = "dt" :style = "dateCalculateDisplay">
    <div>{{today}}</div>
    <div>
      <input v-model="startYear">年
      <input v-model="startMonth">月
      <input v-model="startDay">日
    </div>

    <div>
      <input v-model="endYear">年
      <input v-model="endMonth">月
      <input v-model="endDay">日
      <button v-on:click="handleBtnClick">计算</button>
    </div>

    <div>
      <span>起始日：</span>
      <span>{{startYear}}年</span>
      <span>{{startMonth}}月</span>
      <span>{{startDay}}日</span>
    </div>

    <div>
      <span>截止日：</span>
      <span >{{endYear}}年</span>
      <span >{{endMonth}}月</span>
      <span >{{endDay}}日</span>
    </div>



    <div> time1 is (in milliseconds){{time1}}</div>
    <div> time1 is (in milliseconds){{time2}}</div>
    <div v-if="show"> 投资期限: {{DateBtw}}天</div>
  </div>
</div>  
</template>

<script>

export default {
name: 'DateBtw',
data() {
  return {
    today: undefined,
    startYear: null,
    startMonth: 0,
    startDay:0,
    endYear: 0,
    endMonth: 0,
    endDay:0,
    startDate: '',
    endDate: '',
    time1: 0,
    time2: 0,
    DateBtw: 0,
    show: false,
    dateCalculateDisplay: {
        display: "none"
    }
  }
},
beforemounted() {
  this.today = new Date();
  this.today = this.today.getFullYear();
},
methods: {
  handleDisplayClick() {
    if (this.dateCalculateDisplay.display == "none") {
        this.dateCalculateDisplay.display = "inline";
    } else {
        this.dateCalculateDisplay.display = "none"
      }
  },
  handleBtnClick () {
    this.today = new Date().getFullYear();                this.startDate = new Date(this.startYear,this.startMonth-1,this.startDay);
    this.endDate = new Date(this.endYear,this.endMonth-1,this.endDay);                
    console.log('开始年'+this.startDate.getFullYear());
    console.log('开始月'+this.startDate.getMonth()+1);
    console.log('开始日'+this.startDate.getDate());
    console.log('开始星期'+this.startDate.getDay());
    this.time1 = this.startDate.getTime();
    this.time2 = this.endDate.getTime();
    this.DateBtw = 1 + ((this.time2- this.time1)/(1000*60*60*24));
    console.log(this.DateBtw);
    this.startDate = new Date();
    console.log(this.startDate + 'aaa');
    this.show = true;
  }
},

}
</script>

<style>
h1{
  font-size: 600%;
  color: #FFF;
  }
h2{
    font-size: 200%;
    color: #FFF;
  }
.outter{
  font-size: 100%;
  color: #fff;
}

</style>