<template>
  <div id = "bin-datetime" class = "datetime">
    <h2>Bin</h2>
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
        day: ('0000000'+date.getDate().toString(2)).slice(-8),
        month: ('0000000'+(1+date.getMonth()).toString(2)).slice(-8),
        year: ('0000000'+(date.getFullYear()%100).toString(2)).slice(-8),
        hours: ('0000000'+date.getHours().toString(2)).slice(-8),
        minutes: ('0000000'+date.getMinutes().toString(2)).slice(-8),
        seconds: ('0000000'+date.getSeconds().toString(2)).slice(-8),
      },
      timer: undefined,
    };
  },
  methods: {
    setDateTime() {
      const date = new Date();
      this.dateTime = {
        day: ('0000000'+date.getDate().toString(2)).slice(-8),
        month: ('0000000'+(1+date.getMonth()).toString(2)).slice(-8),
        year: ('0000000'+(date.getFullYear()%100).toString(2)).slice(-8),
        hours: ('0000000'+date.getHours().toString(2)).slice(-8),
        minutes: ('0000000'+date.getMinutes().toString(2)).slice(-8),
        seconds: ('0000000'+date.getSeconds().toString(2)).slice(-8),
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