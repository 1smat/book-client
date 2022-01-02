<template>
  <div class="timer">
    <button @click="setTime">Show time</button>
    <div id="time">{{ time }}</div>
  </div>
</template>

<script>
let today = new Date()
let timer = today.getHours() + ':' + today.getMinutes()

export default {
  data() {
    return {
      time: '',
    }
  },
  methods: {
    setTime() {
      this.time = timer
    },
  },
}
</script>

<style scoped>
.timer {
  margin: 20px 0 0 20px;
}
</style>
