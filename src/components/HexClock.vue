<template>
  <div id = "hex-datetime" class = "datetime">
    <h2>Hex</h2>
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
        day: ("0" + date.getDate().toString(16)).slice(-2),
        month: ("0" + (1+date.getMonth()).toString(16)).slice(-2),
        year: ("0" + (date.getFullYear()%100).toString(16)).slice(-2),
        hours: ("0" + date.getHours().toString(16)).slice(-2),
        minutes: ("0" + date.getMinutes().toString(16)).slice(-2),
        seconds: ("0" + date.getSeconds().toString(16)).slice(-2),
      },
      timer: undefined,
    };
  },
  methods: {
    setDateTime() {
      const date = new Date();
      this.dateTime = {
        day: ("0" + date.getDate().toString(16)).slice(-2),
        month: ("0" + (1+date.getMonth()).toString(16)).slice(-2),
        year: ("0" + (date.getFullYear()%100).toString(16)).slice(-2),
        hours: ("0" + date.getHours().toString(16)).slice(-2),
        minutes: ("0" + date.getMinutes().toString(16)).slice(-2),
        seconds: ("0" + date.getSeconds().toString(16)).slice(-2),
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