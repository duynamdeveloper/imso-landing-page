<template>
  <header class="sans-serif">
    <div
      class="cover bg-left bg-center-l vh-100"
      style="background-image: url(http://letsviettravel.vn/upload/product/201410980154.jpg)"
    >
      <div class="bg-midnightblue-80 pb5 pb6-m pb7-l h-100">
        <nav class="dt w-100 mw9 center">
          <div class="dtc w3 v-mid pa3">
            <a
              href="/"
              class="dib w3 h3 pa1 grow-large border-box"
            >
              <img
                class="link white-90 hover-white"
                src="imso_logo_white_3x5.svg"
              />
              <!-- <title>skull icon</title>
                <path d="M16 0 C6 0 2 4 2 14 L2 22 L6 24 L6 30 L26 30 L26 24 L30 22 L30 14 C30 4 26 0 16 0 M9 12 A4.5 4.5 0 0 1 9 21 A4.5 4.5 0 0 1 9 12 M23 12 A4.5 4.5 0 0 1 23 21 A4.5 4.5 0 0 1 23 12"></path> -->

            </a>
          </div>
          <div class="dtc v-mid tr pa3-l pr0-m">
            <reponsive-menu />
          </div>
        </nav>
        <div class="tc-l mt4 mt5-m mt6-l ph3">
          <countdown
            starttime="Nov 5, 2018 15:37:25"
            endtime="Nov 8, 2019 16:37:25"
          />
          <h1 class="f2 f1-l fw8 ttu white mb0 lh-title">{{ $t('home.title') }}</h1>
          <h2
            class="fw8 f1-l white mt3 mb4 lh-title"
            v-html="$t('home.date')"
          ></h2>
          <h2
            class="fw8 f1-l white mt3 mb4 lh-title"
            v-html="$t('home.location')"
          ></h2>
        </div>
      </div>
    </div>
  </header>
</template>
<script>
import ReponsiveMenu from '~/components/ReponsiveMenu'
import Countdown from '~/components/Countdown'
export default {
  components: { ReponsiveMenu, Countdown }
}
</script>

