<template>

<div class="dib bg-white hide-child bg-animate relative-m relative-l w-100 w-auto-ns">
      <a href="#" class="dt nav tc no-underline pa1 ph4 dark-gray w-100">
          <img :src="`/${locale.flag}`" class="dtc v-mid" width="30px" height="30px">
          <span class="dtc tl v-mid pl2">{{ locale.label }}</span>
      </a>
      <ul class="menu list mt1 bg-white b-yellow f6 child child-vs o-100-vs absolute-m absolute-l top-100-m w-100 br2 shadow-4 pa1" style="left: 0">
        <li class="ma1 pa1 ph3 bg-animate hover-bg-gray pointer w-100" style="display: table" @click="changeLanguage('en')">
      
          <img src="/en_flag.svg" class="dtc v-mid" width="25px" height="25px">
          <span class="dtc tl v-mid">English</span>
         
        </li>
        <li class="ma1 pa1 ph3 bg-animate hover-bg-gray pointer w-100" style="display: table"  @click="changeLanguage('vi')">
          <img src="/vi_flag.svg" class="dtc v-mid" width="25px" height="25px">
          <span class="dtc tl v-mid">Tiếng Việt</span>
        </li>
      </ul>
    </div>
</template>
<script>
export default {
  data(){
    return{
      locale:{
        lang: 'vi',
        label: 'Việt Nam',
        flag: 'vi_flag.svg'
      }
    }
    
  },
  methods:{
    changeLanguage(lang){
      if(lang == 'en'){
        this.locale.lang = 'en'
        this.locale.label = 'English'
        this.locale.flag = 'en_flag.svg'
        this.$store.commit('SET_LANG', lang)
        this.$i18n.locale = lang
      }
      if(lang == 'vi'){
       this.$store.commit('SET_LANG', lang)
        this.locale.lang = 'vi'
        this.locale.label = 'Tiếng Việt'
        this.locale.flag = 'vi_flag.svg'
        this.$i18n.locale = lang
      }
    }
  }
 
 
}
</script>

<style>

.languagepicker {
  display: inline-block;
  padding: 0;
  height: 40px;
  overflow: hidden;
  transition: all 0.3s ease;
  vertical-align: top;
}

.languagepicker:hover {
  /* don't forget the 1px border */
  height: 81px;
}

.languagepicker a {
  color: #000;
  text-decoration: none;
}

.languagepicker li {
  display: block !important;
  padding: 0px 20px !important;
  line-height: 40px;
  border-top: 1px solid #eee;
  text-align: left;
}

.languagepicker li:hover {
  background-color: #eee;
}

.languagepicker a:first-child li {
  border: none;
}

.languagepicker li img {
  margin-right: 5px;
}

.roundborders {
  border-radius: 5px;
}

.large:hover {
  /* 
	don't forget the 1px border!
	The first language is 40px heigh, 
	the others are 41px
	*/
  height: 245px;
}
</style>
