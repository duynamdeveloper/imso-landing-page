<template>

  <section
    class="pa4 bg-gradient-overlay"
    id="agenda"
  >
    <header class="tc ph4 pa4">
      <h1 class="f2 f2-m f2-l fw7 white ttu mv3">{{ $t("home.proposed_agenda.title") }}</h1>
      <!-- <h2
        class="f5 f4-m f3-l fw2 black-50 mt0 lh-copy"
      >This is the subtitle where additional information can go if you really need it.</h2>-->
    </header>
    <div class="overflow-auto">
      <div class="tabs mw8 center mt2">
        <div class="tabs__menu flex mb5">
          <label class="w-20-ns w-0"></label>
          <label
            for="section1"
            class="tabs__menu-item w-30-ns w-50 tc bg-midnightblue br4 pt4 pb4 pointer white f4 ttu b mr2"
            :class="{'bg-red': isActive}"
            @click="toggleActive"
          >{{ $t("common.contestants") }}</label>
          <label
            for="section2"
            class="tabs__menu-item w-30-ns w-50 bg-midnightblue br4 tc pt4 pb4 bg-animate pointer f4 white ttu b"
            :class="{'bg-red': !isActive}"
            @click="toggleActive"
          >
            {{ $t("common.officials") }}
          </label>
        </div>
        <div class="tabs__content ">
          <div>
            <input
              type="radio"
              class="dn"
              name="sections"
              id="section1"
              checked
            >
            <div class="tabs__content__info animated fadeInRight">
              <ul class="list pl0 mt0 center">
                <li class="cf lh-copy pa0 ph0-l ba b--black-10 bg-white-80 br4 mt3">

                  <div
                    class="pl3 w-30-ns fl w-100 h-100 tl-ns tc b bg-purple-80 pa4-ns pa3 br4 white h4-ns"
                    v-html="$t('home.proposed_agenda.timeline.time.day1')"
                  ></div>
                  <div class="pl3 tc w-70-ns w-100 fl pa4 h-100 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.all_day')}}</h3>
                    <h4 class="f4 db">{{$t('home.proposed_agenda.timeline.contestant.day1.content_1')}}</h4>
                  </div>

                </li>
                <li class="cf lh-copy pa0 ph0-l ba b--black-10 bg-white-80 br4 mt3-ns mt3">

                  <div
                    class="pl3 w-30-ns fl w-100 tl-ns tc b bg-purple-80 pa4-ns pa3 br4 white h4-ns"
                    v-html="$t('home.proposed_agenda.timeline.time.day2')"
                  ></div>
                  <div class="pl3 tc w-40-ns w-100 fl pa4 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.morning')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.contestant.day2.content_1')}}</h4>
                  </div>
                  <div class="pl3 tc w-30-ns w-100 fl pa4 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.afternoon')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.contestant.day2.content_2')}}</h4>
                  </div>

                </li>
                <li class="cf lh-copy pa0 ph0-l ba b--black-10 bg-white-80 br4 mt3-ns mt2">

                  <div
                    class="pl3 w-30-ns fl w-100 tl-ns tc b bg-purple-80 pa4-ns pa3 br4 white h4-ns"
                    v-html="$t('home.proposed_agenda.timeline.time.day3')"
                  ></div>
                  <div class="pl3 tc w-40-ns w-100 fl pa4 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.morning')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.contestant.day3.content_1')}}</h4>
                  </div>
                  <div class="pl3 tc w-30-ns w-100 fl pa4 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.afternoon')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.contestant.day3.content_2')}}</h4>
                  </div>

                </li>
                <li class="cf lh-copy pa0 ph0-l ba b--black-10 bg-white-80 br4 mt3-ns mt2">

                  <div
                    class="pl3 w-30-ns fl w-100 h4-ns tl-ns tc b bg-purple-80 pa4-ns pa3 br4 white"
                    v-html="$t('home.proposed_agenda.timeline.time.day4')"
                  ></div>
                  <div class="pl3 tc w-25-ns w-100 h4-ns fl pa4">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.morning')}}</h3>
                    <h4 class="f5 db black">{{$t('home.proposed_agenda.timeline.contestant.day4.content_1')}}</h4>
                  </div>
                  <div class="pl3 tc w-25-ns w-100 h4-ns fl pa4">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.afternoon')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.contestant.day4.content_2')}}</h4>
                  </div>
                  <div class="pl3 tc w-20-ns w-100 h4-ns fl pa4">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.night')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.contestant.day4.content_3')}}</h4>
                  </div>
                </li>
                <li class="cf lh-copy pa0 ph0-l ba b--black-10 bg-white-80 br4 mt3-ns mt3">

                  <div
                    class="pl3 w-30-ns fl w-100 tl-ns tc b bg-purple-80 pa4-ns pa3 br4 white h4-ns"
                    v-html="$t('home.proposed_agenda.timeline.time.day5')"
                  ></div>
                  <div class="pl3 tc w-40-ns w-100 fl pa4 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.morning')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.contestant.day5.content_1')}}</h4>
                  </div>
                  <div class="pl3 tc w-30-ns w-100 fl pa4 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.afternoon')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.contestant.day5.content_2')}}</h4>
                  </div>

                </li>
                <li class="cf lh-copy pa0 ph0-l ba b--black-10 bg-white-80 br4 mt3">

                  <div
                    class="pl3 w-30-ns fl w-100 h-100 tl-ns tc b bg-purple-80 pa4-ns pa3 br4 white h4-ns"
                    v-html="$t('home.proposed_agenda.timeline.time.day6')"
                  ></div>
                  <div class="pl3 tc w-70-ns w-100 fl pa4 h-100 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.all_day')}}</h3>
                    <h4 class="f4 db">{{$t('home.proposed_agenda.timeline.contestant.day6.content_1')}}</h4>
                  </div>

                </li>
              </ul>
            </div>
          </div>
          <div>
            <input
              type="radio"
              class="dn"
              name="sections"
              id="section2"
            >
            <div class="tabs__content__info animated fadeInRight">
              <ul class="list pl0 mt0 center">
                <li class="cf lh-copy pa0 ph0-l ba b--black-10 bg-white-80 br4 mt3">

                  <div
                    class="pl3 w-30-ns fl w-100 h-100 tl-ns tc b bg-purple-80 pa4-ns pa3 br4 white h4-ns"
                    v-html="$t('home.proposed_agenda.timeline.time.day1')"
                  ></div>
                  <div class="pl3 tc w-70-ns w-100 fl pa4 h-100 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.all_day')}}</h3>
                    <h4 class="f4 db">{{$t('home.proposed_agenda.timeline.official.day1.content_1')}}</h4>
                  </div>

                </li>
                <li class="cf lh-copy pa0 ph0-l ba b--black-10 bg-white-80 br4 mt3-ns mt3">

                  <div
                    class="pl3 w-30-ns fl w-100 tl-ns tc b bg-purple-80 pa4-ns pa3 br4 white h4-ns"
                    v-html="$t('home.proposed_agenda.timeline.time.day2')"
                  ></div>
                  <div class="pl3 tc w-40-ns w-100 fl pa4 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.morning')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.official.day2.content_1')}}</h4>
                  </div>
                  <div class="pl3 tc w-30-ns w-100 fl pa4 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.afternoon')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.official.day2.content_2')}}</h4>
                  </div>

                </li>
                <li class="cf lh-copy pa0 ph0-l ba b--black-10 bg-white-80 br4 mt3-ns mt2">

                  <div
                    class="pl3 w-30-ns fl w-100 tl-ns tc b bg-purple-80 pa4-ns pa3 br4 white h4-ns"
                    v-html="$t('home.proposed_agenda.timeline.time.day3')"
                  ></div>
                  <div class="pl3 tc w-40-ns w-100 fl pa4 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.morning')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.official.day3.content_1')}}</h4>
                  </div>
                  <div class="pl3 tc w-30-ns w-100 fl pa4 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.afternoon')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.official.day3.content_2')}}</h4>
                  </div>

                </li>
                <li class="cf lh-copy pa0 ph0-l ba b--black-10 bg-white-80 br4 mt3-ns mt2">

                  <div
                    class="pl3 w-30-ns fl w-100 h4-ns tl-ns tc b bg-purple-80 pa4-ns pa3 br4 white"
                    v-html="$t('home.proposed_agenda.timeline.time.day4')"
                  ></div>
                  <div class="pl3 tc w-25-ns w-100 h4-ns fl pa4">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.morning')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.official.day4.content_1')}}</h4>
                  </div>
                  <div class="pl3 tc w-25-ns w-100 h4-ns fl pa4">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.afternoon')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.official.day4.content_2')}}</h4>
                  </div>
                  <div class="pl3 tc w-20-ns w-100 h4-ns fl pa4">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.night')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.official.day4.content_3')}}</h4>
                  </div>
                </li>
                <li class="cf lh-copy pa0 ph0-l ba b--black-10 bg-white-80 br4 mt3-ns mt3">

                  <div
                    class="pl3 w-30-ns fl w-100 tl-ns tc b bg-purple-80 pa4-ns pa3 br4 white h4-ns"
                    v-html="$t('home.proposed_agenda.timeline.time.day5')"
                  ></div>
                  <div class="pl3 tc w-40-ns w-100 fl pa4 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.morning')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.official.day5.content_1')}}</h4>
                  </div>
                  <div class="pl3 tc w-30-ns w-100 fl pa4 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.afternoon')}}</h3>
                    <h4 class="f4 db black">{{$t('home.proposed_agenda.timeline.official.day5.content_2')}}</h4>
                  </div>

                </li>
                <li class="cf lh-copy pa0 ph0-l ba b--black-10 bg-white-80 br4 mt3">

                  <div
                    class="pl3 w-30-ns fl w-100 h-100 tl-ns tc b bg-purple-80 pa4-ns pa3 br4 white h4-ns"
                    v-html="$t('home.proposed_agenda.timeline.time.day6')"
                  ></div>
                  <div class="pl3 tc w-70-ns w-100 fl pa4 h-100 h4-ns">
                    <h3 class="f5 db red b">{{$t('home.proposed_agenda.timeline.time.all_day')}}</h3>
                    <h4 class="f4 db">{{$t('home.proposed_agenda.timeline.official.day6.content_1')}}</h4>
                  </div>

                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

</template>
<script>
export default {
  data() {
    return {
      isActive: true
    }
  },
  methods: {
    toggleActive() {
      this.isActive = !this.isActive
    }
  }
}
</script>

