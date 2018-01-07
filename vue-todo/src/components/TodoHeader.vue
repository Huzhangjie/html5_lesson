<template>
  <div class="todo-header">
      <div class="overlay"></div>
      <time class="clearfix">
        <span class="day">{{ date }}</span>
        <span class="dayofweek">{{ weekDay }}</span>
        <span class="month">{{ month }}, {{ year }}</span>
      </time>
      <div class="add-circle" @click="add">
        <i class="fa fa-plus"></i>
      </div>
  </div>
</template>
<style></style>
<script>
  const month = ["January", "February", "Mach", "April", "May", "June", "July", "August", "September", "October", "November", "September"],
    weekday = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
  export default {
    data() {
      return {
        date: '',
        weekDay: '',
        month: '',
        year: ''
      }
    },
    // beforeCreated之前 created之后
    // mounted元素挂载到页面之后 beforeMounted用户看到之前
    // 生命周期就是钩子函数 在特定的时期发生
    created() {
      const d = new Date()
      this.date = d.getDate()
      this.weekDay = weekday[d.getDay()]
      this.month = month[d.getMonth()]
      this.year = d.getFullYear()
    },
    methods: {
      add() {
        console.log('add')
      }
    }
  }
</script>