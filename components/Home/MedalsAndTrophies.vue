<template>
  <section
    class="bg-midnightblue white false bb b--black-10 flex flex-column flex-row-l items-stretch justify-stretch"
    id="prize"
  >
    <div class="flex w-50-l items-center justify-center false pa5-l pa4"><img
        class="luminous"
        :src="`${$axios.defaults.baseURL}contestants_bg.jpg`"
      >
    </div>
    <div class=" pa5-ns flex w-50-l items-center content-start justify-center-ns justify-start false">
      <div class="pl3-l ph4-m pv2-ns pv4 ph3 w-60-m">
        <h3 class="f2-ns mb3 lh-title ttu b pv2-ns white">{{ $t("home.medals_trophies.title") }}</h3>
        <ul class="f4">
          <li
            class="lh-copy"
            v-for="(text, index) in $t('home.medals_trophies.content')"
            :key="index"
            v-html="text"
          ></li>
        </ul>

      </div>
    </div>

  </section>
</template>
