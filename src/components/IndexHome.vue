<template>
  <div style="text-align: center">
    <h1>{{ title }}</h1>
    <h3>当前时间: <date-object :date="now" simple="yyyy-MM-dd hh:mm:ss"></date-object></h3>
  </div>

</template>

<script>
import DateObject from "../common/DateObject";
export default {
  name: "IndexHome",
  components: {
    DateObject
  },
  data() {
    return {
      title: "Our Story | 我们的故事",
      timer: null,
      now: new Date()
    }
  },
  created() {
    this.timer = this.loadDateTimer()
  },
  methods: {
    loadDateTimer() {
      setInterval(() => {
        this.now = new Date()
      }, 1000)
    }
  }
}
</script>

<style scoped>

</style>
