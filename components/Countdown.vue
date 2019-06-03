/*
* Created by Negar Jamalifard at Yasna Team
* On 2018-03-11
* Codepen: https://codepen.io/negarjf
* Github: https://github.com/negarjf
* Email: n.jamalifatd@gmail.com
* 
*/ 

<template>
  <div class="timer">
    <div v-show="statusType !== 'expired'" class="timer-container">
      <div class="day">
        <span class="number fw7">{{ days }}</span>
        <div class="format ttc">{{ $t("timer.day") }}</div>
      </div>
      <div class="hour">
        <span class="number fw7">{{ hours }}</span>
        <div class="format ttc">{{ $t("timer.hour") }}</div>
      </div>
      <div class="min">
        <span class="number fw7">{{ minutes }}</span>
        <div class="format ttc">{{ $t("timer.minute") }}</div>
      </div>
      <div class="sec">
        <span class="number fw7">{{ seconds }}</span>
        <div class="format ttc">{{ $t("timer.second") }}</div>
      </div>
    </div>
  </div>
</template>
  <script>
export default {
  props: ['starttime', 'endtime', 'trans'],
  data: function() {
    return {
      timer: '',
      start: '',
      end: '',
      interval: '',
      days: '',
      minutes: '',
      hours: '',
      seconds: '',
      message: '',
      statusType: '',
      statusText: ''
    }
  },
  created: function() {},
  mounted() {
    this.start = new Date(this.starttime).getTime()
    this.end = new Date(this.endtime).getTime()
    // Update the count down every 1 second
    this.timerCount(this.start, this.end)
    this.interval = setInterval(() => {
      this.timerCount(this.start, this.end)
    }, 1000)
  },
  methods: {
    timerCount: function(start, end) {
      // Get todays date and time
      var now = new Date().getTime()

      // Find the distance between now an the count down date
      var distance = start - now
      var passTime = end - now

      if (distance < 0 && passTime < 0) {
        this.message = 'Expired'
        this.statusType = 'expired'
        this.statusText = 'Expired'
        clearInterval(this.interval)
        return
      } else if (distance < 0 && passTime > 0) {
        this.calcTime(passTime)
        this.message = 'Running'
        this.statusType = 'running'
        this.statusText = 'Running'
      } else if (distance > 0 && passTime > 0) {
        this.calcTime(distance)
        this.message = 'Upcoming'
        this.statusType = 'upcoming'
        this.statusText = 'Upcoming'
      }
    },
    calcTime: function(dist) {
      // Time calculations for days, hours, minutes and seconds
      this.days = Math.floor(dist / (1000 * 60 * 60 * 24))
      this.hours = Math.floor((dist % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
      this.minutes = Math.floor((dist % (1000 * 60 * 60)) / (1000 * 60))
      this.seconds = Math.floor((dist % (1000 * 60)) / 1000)
    }
  }
}
</script>
<style lang="scss">
.timer {
  font-size: 20px;
  color: #fff;
  text-align: center;
  margin-top: 50px;

  .day,
  .hour,
  .min,
  .sec {
    margin: 0 30px;
    font-size: 28px;
    display: inline-block;
    font-weight: 500;
    text-align: center;
    width: 65px;
    height: 60px;
    line-height: 60px;
    border-radius: 3px;
    margin-bottom: 15px;
    // display: block;
    color: #fff;
    .format {
      font-weight: 300;
      font-size: 20px;
      //@include margin-start(5);
      //display: inline-block;
      opacity: 0.8;
      width: 60px;
    }
  }
  .day {
    .number {
      background: #f44336;
      background: -moz-linear-gradient(145deg, #f44336 0%, #d84315 100%);
      background: -webkit-linear-gradient(145deg, #f44336 0%, #d84315 100%);
      background: linear-gradient(145deg, #f44336 0%, #d84315 100%);
    }
    .format {
      color: #f44336;
    }
  }
  .hour {
    .number {
      background: #03a9f4;
      background: -moz-linear-gradient(145deg, #03a9f4 0%, #1e88e5 100%);
      background: -webkit-linear-gradient(145deg, #03a9f4 0%, #1e88e5 100%);
      background: linear-gradient(145deg, #03a9f4 0%, #1e88e5 100%);
    }
    .format {
      color: #8bc34a;
    }
  }
  .min {
    .number {
      background: #8bc34a;
      background: -moz-linear-gradient(145deg, #8bc34a 0%, #689f38 100%);
      background: -webkit-linear-gradient(145deg, #8bc34a 0%, #689f38 100%);
      background: linear-gradient(145deg, #8bc34a 0%, #689f38 100%);
    }
    .format {
      color: #03a9f4;
    }
  }
  .sec {
    .number {
      background: #ffc107;
      background: -moz-linear-gradient(145deg, #ffc107 0%, #f57f17 100%);
      background: -webkit-linear-gradient(145deg, #ffc107 0%, #f57f17 100%);
      background: linear-gradient(145deg, #ffc107 0%, #f57f17 100%);
    }
    .format {
      color: #ffc107;
    }
  }
  .number {
    background: rgba(51, 51, 51, 0.53);
    padding: 0 5px;
    border-radius: 5px;
    display: inline-block;
    width: 60px;
    text-align: center;
  }
  .message {
    font-size: 14px;
    font-weight: 400;
    margin-top: 5px;
  }
  .status-tag {
    width: 270px;
    margin: 10px auto;
    padding: 8px 0;
    font-weight: 500;
    color: #000;
    text-align: center;
    border-radius: 15px;
    &.upcoming {
      background-color: lightGreen;
    }
    &.running {
      background-color: gold;
    }
    &.expired {
      background-color: silver;
    }
  }
}
</style>
  
  
 
