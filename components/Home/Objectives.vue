<template>
  <div
    class=""
    id="objective"
  >
    <div class="dt center pt0 pb5 pv5-m pv4-ns">
      <div class="db dtc-ns v-mid ph2 pr5-ns pl3-ns">
        <header class="bb b--black-70 pv4">
          <h3 class="f3-m f2-ns ttu mv3 b red tracked lh-title mt0 mb3">{{ $t("home.objectives.title") }}</h3>
          <h4 class="f4 fw5 sub-title mt0">{{ $t("home.objectives.subtitle") }}</h4>
        </header>
        <section class="pt5 pb4">
          <div class="lh-copy measure f4 mt0">
            <ul>
              <li
                v-for="(list,index) in $t('home.objectives.content')"
                :key="index"
              >{{ list }}</li>
            </ul>
          </div>
        </section>
      </div>
      <div class="db dtc-ns v-mid-ns mw7">
        <img
          :src="`${$axios.defaults.baseURL}/5V2A0101.JPG`"
          alt="A bright blue sky"
          class="w-90"
        >
      </div>
    </div>
  </div>
</template>
<script>
import Countdown from '~/components/Countdown'
export default {
  components: { Countdown }
}
</script>

