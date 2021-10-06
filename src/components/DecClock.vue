<template>
  <div id = "dec-datetime" class = "datetime">
    <h2>Dec</h2>
    <p class = "time-display">{{ dateTime.month}} {{ dateTime.day}} {{ dateTime.year }}<br>
    {{ dateTime.hours }}_{{ dateTime.minutes }}_{{ dateTime.seconds }}</p>
  </div>
</template>

<script>
const date = new Date();
export default {
  name: "HexClock",
  data() {
    return {
      dateTime: {
        day: ("0" + date.getDate().toString()).slice(-2),
        month: ("0" + (1+date.getMonth()).toString()).slice(-2),
        year: ("0" + (date.getFullYear()%100).toString()).slice(-2),
        hours: ("0" + date.getHours().toString()).slice(-2),
        minutes: ("0" + date.getMinutes().toString()).slice(-2),
        seconds: ("0" + date.getSeconds().toString()).slice(-2),
      },
      timer: undefined,
    };
  },
  methods: {
    setDateTime() {
      const date = new Date();
      this.dateTime = {
        day: ("0" + date.getDate().toString()).slice(-2),
        month: ("0" + (1+date.getMonth()).toString()).slice(-2),
        year: ("0" + (date.getFullYear()%100).toString()).slice(-2),
        hours: ("0" + date.getHours().toString()).slice(-2),
        minutes: ("0" + date.getMinutes().toString()).slice(-2),
        seconds: ("0" + date.getSeconds().toString()).slice(-2),
      };
    },
  },
  beforeMount() {
    this.timer = setInterval(this.setDateTime, 1000);
  },
  beforeUnmount() {
    clearInterval(this.timer);
  },
};
</script>
