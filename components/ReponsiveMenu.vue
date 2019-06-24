<template>
  <nav
    id="site-navigation"
    aria-label="Menu"
    class="z-5 h4-l"
  >
    <label
      for="toggle-mobile-menu"
      aria-label="Menu"
    >&#9776;</label>
    <input
      id="toggle-mobile-menu"
      type="checkbox"
    >

    <ul
      id="main-menu"
      class="z-5"
    >
      <li
        v-for="(item,index) in $t('navbar')"
        :key="index"
      >
        <a
          class="f5 hover-bg-red no-underline white dib-ns pv2 ph3 b br2 ttu"
          href="#"
          v-scroll-to="`#${index}`"
        >{{ item }}</a>
      </li>
      
 <!-- <language-picker /> -->
    </ul>

  </nav>
</template>
<script>
import LanguagePicker from '~/components/LanguagePicker'
export default {
  components: { LanguagePicker },
  data() {
    return {
      lang: 'en'
    }
  }
}
</script>

<style>
@media only screen and (max-width: 600px) {
  #main-menu{
    position: absolute;
    right: 0px;
    top: 0px;
  }
}
#site-navigation {
  display: block;
  height: 48px;
}

#site-navigation #main-menu,
#site-navigation > input {
  display: none;
}

#site-navigation > label {
  display: block;
  font-size: 36px;
  color: #fff;
  position: absolute;
  right: 20px;
  width: 36px;
  padding: 0;
  cursor: pointer;
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

#site-navigation > input:checked + #main-menu {
  display: block;
  clear: both;
  top: 36px;
  position: relative;
  background: #000;
  color: #fff;
}

#site-navigation ul li {
  display: block;
  padding: 12px 10px;
}

@media only screen and (min-device-width: 768px) {
  #site-navigation #main-menu {
    display: block;
  }
  #site-navigation > label {
    display: none;
  }
  #site-navigation ul li {
    display: inline-block;
  }
}
</style>
