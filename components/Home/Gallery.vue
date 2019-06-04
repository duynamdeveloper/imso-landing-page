<template>
  <section
    class="bg-midnightblue"
    id="gallery"
  >
    <!-- <LightGallery
      :images="images"
      :index="index"
      :disable-scroll="true"
      @close="index = null"
    /> -->
    <div class="mw9 center ph3-ns pv5">
      <h3 class="f2-ns f4 white ttu pb5 b center tc">gallery</h3>
      <div class="cf ph2-ns">
        <div
          class=" fl w-100 w-third-ns pa2"
          v-for="(thumb, thumbIndex) in images"
          :key="thumbIndex"
        >
          <div class="pointer"><img
              class="db w-100 grow"
              :src="$axios.defaults.baseURL+thumb.url"
              @click="index = thumbIndex"
            /></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      images: [
        { title: 'IMSO 2018', url: '/gallery/01.JPG' },
        { title: 'IMSO 2018', url: '/gallery/02.JPG' },
        { title: 'IMSO 2018', url: '/gallery/03.JPG' },
        { title: 'IMSO 2018', url: '/gallery/04.JPG' },
        { title: 'IMSO 2018', url: '/gallery/05.JPG' },
        { title: 'IMSO 2018', url: '/gallery/06.JPG' }
      ],
      index: null
    }
  }
}
</script>