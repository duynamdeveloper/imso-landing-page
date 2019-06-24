<template>
  <header class="sans-serif">
     <div class="slider">
    <ul class="slides" :style="style">
      <li v-for="(slide,i) in playslides" :key="i">
        <div class="img" :style="{ backgroundImage: `url(${slide.img})` }"></div>
      </li>
    </ul>
     </div>
    </div>
      <div class="bg-midnightblue-30 pb5 pb6-m pb7-l h-100 w-100" style="position: absolute; top: 0; left: 0">
        <nav class="dt w-100 mw9 center">
          <div class="dtc w3 v-mid pa3">
            <a
              href="/"
              class="dt w3 h3 pa1 border-box"
            >
              <img
                class="link white-90 hover-white dtc"
                src="/imso_logo_white.png"
                alt="IMSO 2019 Logo"
                title="IMSO 2019"
              />
             
              <!-- <title>skull icon</title>
                <path d="M16 0 C6 0 2 4 2 14 L2 22 L6 24 L6 30 L26 30 L26 24 L30 22 L30 14 C30 4 26 0 16 0 M9 12 A4.5 4.5 0 0 1 9 21 A4.5 4.5 0 0 1 9 12 M23 12 A4.5 4.5 0 0 1 23 21 A4.5 4.5 0 0 1 23 12"></path> -->

            </a>
          </div>
          <div class="dtc w2 v-mid pa2 pv1">
            <a
              href="/"
              class="dt w5 h2 pa1 border-box"
            >
              <img
                class="link white-90 hover-white dtc"
                src="/imso_vietnam_logo_no_bg.png"
                height="80px"
                alt="IMSO 2019 Logo"
                title="IMSO 2019"
              />
             
          </a>
          
          </div>
          <div class="dtc v-mid tr pa3-l pr0-m">
            <reponsive-menu />
          </div>
           <!-- <div class="dtc v-mid tr pa3-l pr0-m">
                   <language-picker />
           </div> -->
    
        </nav>
        <div class="tc-l mt4 mt5-m mt6-l ph3">
          <countdown
            starttime="Nov 5, 2018 15:37:25"
            endtime="Nov 8, 2019 16:37:25"
          />
          <h1 class="f2 f1-l fw8 ttu white mb0 lh-title">{{ $t('home.title') }}</h1>
          <h2
            class="fw8 f1-l white mt3 mb4 lh-title ttc"
            v-html="$t('home.date')"
          ></h2>
          <h2
            class="fw8 f1-l white mt3 mb4 lh-title ttc"
            v-html="$t('home.location')"
          ></h2>
        </div>
      </div>
    
  </header>
</template>
<script>
import ReponsiveMenu from '~/components/ReponsiveMenu'
import Countdown from '~/components/Countdown'
import LanguagePicker from '~/components/LanguagePicker'

export default {
  components: { ReponsiveMenu, Countdown, LanguagePicker },
    data() {
    return{
    slides: [
      {
        img:
          "https://ihworld.com/media/1967/hanoi-vietnam.jpg?crop=0,0.23573573573573575,0,0.060435435435435475&cropmode=percentage&width=1600&height=750",

      },
      {
        img:
          "/hanoi.jpg",
      
      },
      {
        img:
          "https://cdn.asiatatler.com/asiatatler/i/hk/2018/11/06203306-story-image-11940_cover_2000x1200.jpg",
     
      },
      {
        img:
          "https://images.unsplash.com/photo-1466150036782-869a824aeb25?dpr=1&auto=format&fit=crop&w=1500&h=1000&q=80&cs=tinysrgb&crop=",
       
      }
    ],
    
    current: 0,
    percent: 0,
    timer: 0,
    interval: 0,
    progress: 0,
    duration: 5000,
    playslides: []
    }
  },
  computed: {
    style() {
      switch (this.current % 2) {
        case 0:
          return { top: "0" };
        case 1:
          return { top: "-100%" };
      }
    }
  },
  methods: {
    selectSlide(i) {
      this.current = i;
      this.playslides[this.current % 2] = this.slides[this.current];
      this.resetPlay();
    },
    process() {
      this.current++;
      if (this.current >= this.slides.length) {
        this.current = 0;
      }
      this.playslides[this.current % 2] = this.slides[this.current];
      this.resetPlay();
    },
    going() {
      let time = new Date().getTime();
      this.percent = Math.floor(100 * (time - this.timer) / this.duration);
    },
    resetPlay() {
      clearInterval(this.interval);
      clearInterval(this.progress);
      this.play();
    },
    stop() {
      clearInterval(this.interval);
      clearInterval(this.progress);
    },
    play() {
      this.timer = new Date().getTime();
      this.progress = setInterval(this.going, this.duration / 100);
      this.interval = setInterval(this.process, this.duration);
    }
  },
  created() {
    for(let i = 0; i< this.slides.length; i++){
      this.playslides[i] = this.slides[i]
    }
    this.play();
  }
}
</script>
<style lang="stylus">
.slider
  position: relative
  z-index: -1
  overflow: hidden
  height: 100vh
  ul
    list-style: none
    &.slides
      position: absolute
      width: 100%
      height: 100%
      margin: 0
      padding: 0
      transition: all 0.8s ease
      li
        height: 100%
        .img
          height: 100%
          background-size: cover
          background-position: 50%

</style>


