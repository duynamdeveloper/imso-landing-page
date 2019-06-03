<template>
  <div class="bg-midnight-blue">
    <div class="dt mw9 center pt0 pa5 pv5-m pv5-ns">
      <div class="dtc-ns v-mid ph2 pr5-ns pl3-ns">
        <header class="pt0 pb3 tc">
          <h3 class="f2 f2-m f2-l fw7 red ttu mv3 tracked mt0 mb3 avenir">{{ $t("home.contestants_officials.title") }}</h3>
          <!-- <h4 class="f4 fw5 sub-title mt0 ">{{ $t("home.objectives.subtitle") }}</h4> -->
        </header>

        <div class="cf f4 ph2-ns">
          <div class="fl w-100 w-50-ns">
            <h4 class="tc f3 b pv3 ttc ">{{$t("common.contestants")}}</h4>
            <ul>
              <li
                class="lh-copy"
                v-for="(text, index) in $t('home.contestants_officials.contestants')"
                :key="index"
                v-html="text"
              ></li>
            </ul>
          </div>
          <div class="fl w-100 w-50-ns">
            <h4 class="b f3 pv3 ttc tc">{{$t("common.officials")}}</h4>
            <ul>
              <li
                class="lh-copy"
                v-for="(text, index) in $t('home.contestants_officials.officials')"
                :key="index"
                v-html="text"
              ></li>
            </ul>
          </div>
        </div>

      </div>

    </div>
  </div>
</template>
<script>
</script>

