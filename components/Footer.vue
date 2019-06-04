<template>
  <footer class="pv4 ph3 ph5-m ph6-l bg-midnightblue-darken w-100">
    <article class="mw4  mw4-ns center">
      <div class="aspect-ratio aspect-ratio--9x16 mb2">
        <div
          class="aspect-ratio--object cover"
          :style="`background:url(${$axios.defaults.baseURL}imso_logo_white_3x5.png) center;`"
        ></div>
      </div>

    </article>
    <h1 class="tc white ttu lh-title f2-ns mv1">IMSO 2019</h1>
    <h2 class="tc white ttu lh-title f3-ns">16<sup>th</sup> {{$t("common.title")}}</h2>

    <div class="tc mt3">
      <a
        href="javascript:void(0)"
        class="f6 dib ph2 link gray dim ttc"
      >
        <language-picker /></a>

      <a
        v-for="(item,index) in $t('navbar')"
        :key="index"
        href="#"
        v-scroll-to="`#${index}`"
        :title="item"
        class="f6 dib ph2 link gray dim ttc"
      >{{item}}</a>

    </div>
    <small class="f6 db tc gray pv2">© 2019 <b class="ttc">{{$t("common.hanoi_education_department")}}</b>, All Rights Reserved</small>
  </footer>
</template>

<script>
import LanguagePicker from '~/components/LanguagePicker'
export default {
  components: { LanguagePicker }
}
</script>

<style>
</style>
