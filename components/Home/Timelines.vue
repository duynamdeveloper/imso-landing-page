<template>
  <section
    class="pa6-m pa4 bg-gradient-overlay"
    id="timelines"
  >
    <header class="tc ph4 pa4">
      <h1 class="f2 f2-m f2-l fw7 white ttu mv3">{{ $t("home.timelines.title") }}</h1>
      <!-- <h2
        class="f5 f4-m f3-l fw2 black-50 mt0 lh-copy"
      >This is the subtitle where additional information can go if you really need it.</h2>-->
    </header>
  <div class="mw8-l tj center lh-copy f4 mt0">
      <ul>
          <li v-for="(list,index) in $t('home.timelines.content')" :key="index" v-html="list"></li>
      </ul>
  </div>

  </section>

</template>
<script>
export default {
    
  }
</script>

