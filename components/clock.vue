<template>
  <div id="clock">
    <p class="date">{{ formDt.date }}</p>
    <p class="time">{{ formDt.time }}</p>
  </div>
</template> 

<script>
export default {
  name: 'clock',
  data() {
    return {
      week: ['SUN', 'MON', 'TUE', 'WED', 'THU', 'FRI', 'SAT'],
      datetime: new Date(),
      formDt: {
        time: '',
        date: ''
      }
    }
  },
  created() {
  },
  mounted() {
    this.$options.interval = setInterval(this.updateDt, 1000)
  },
  beforeDestroy() {
    clearInterval(this.$options.interval)
  },
  methods: {
    updateDt: function() {
      let dat = new Date()
      let hours = dat.getHours()
      let mins = dat.getMinutes()
      let sec = dat.getSeconds()
      let day = this.week[dat.getDay()]
      this.formDt.date =
        dat.getFullYear() +
        '-' +
        dat.getMonth() +
        '-' +
        dat.getDay() +
        ' ' +
        day
      this.formDt.time = hours + ':' + mins + ':' + sec
      console.log(this.formDt.date)
      console.log(this.formDt.time)
    },
    zeroPadding(num, digit) {
      let zero = ''
      for (let i = 0; i < digit; i++) {
        zero += '0'
      }
      return (zero + num).slice(-digit)
    },
    updateTime(week) {
      let currentDate = new Date()
      this.clock.time =
        this.zeroPadding(currentDate.getHours(), 2) +
        ':' +
        this.zeroPadding(currentDate.getMinutes(), 2) +
        ':' +
        this.zeroPadding(currentDate.getSeconds(), 2)
      this.clock.date =
        this.zeroPadding(currentDate.getFullYear(), 4) +
        '-' +
        this.zeroPadding(currentDate.getMonth() + 1, 2) +
        '-' +
        this.zeroPadding(currentDate.getDate(), 2) +
        ' ' +
        week[currentDate.getDay()]
    }
  }
}
</script>

<style lang="scss" scoped>
html,
body {
  height: 100%;
}
body {
  background: #0f3854;
  background: radial-gradient(ellipse at center, #0a2e38 0%, #000000 70%);
  background-size: 100%;
}
p {
  margin: 0;
  padding: 0;
}
#clock {
  font-family: 'Share Tech Mono', monospace;
  color: #ffffff;
  text-align: center;
  position: relative;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -15%);
  color: #daf6ff;
  text-shadow: 0 0 20px rgba(10, 175, 230, 1), 0 0 20px rgba(10, 175, 230, 0);
  .time {
    letter-spacing: 0.05em;
    font-size: 80px;
    padding: 5px 0;
  }
  .date {
    letter-spacing: 0.1em;
    font-size: 24px;
  }
  .text {
    letter-spacing: 0.1em;
    font-size: 12px;
    padding: 20px 0 0;
  }
}
</style>
