<template>
  <div>
    <landing-header />
    <objectives />
    <contestants-demo />
    <regulations />
    <medals-and-trophies />
    <proposed-agenda />
    <gallery />
    <vue-footer />
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import LandingHeader from '~/components/Header/LandingHeader.vue'
import Objectives from '~/components/Home/Objectives.vue'
import ProposedAgenda from '~/components/Home/ProposedAgenda.vue'
import ContestantsAndOfficials from '~/components/Home/ContestantsAndOfficials'
import ContestantsDemo from '~/components/Home/ContestantsDemo'
import Regulations from '~/components/Home/Regulations'
import MedalsAndTrophies from '~/components/Home/MedalsAndTrophies'
import Gallery from '~/components/Home/Gallery'
import Footer from '~/components/Footer'
export default {
  name: 'Index',
  components: {
    Logo,
    LandingHeader,
    Objectives,
    ProposedAgenda,
    ContestantsAndOfficials,
    Regulations,
    ContestantsDemo,
    MedalsAndTrophies,
    Gallery,
    VueFooter: Footer
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
