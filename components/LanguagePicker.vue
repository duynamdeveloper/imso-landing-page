<template>
  <ul
    class="languagepicker roundborders bg-white-80"
    style="width: 10rem"
  >
    <NuxtLink :to="`/en` + $route.fullPath">
      <li class="black"><img
          class="v-mid"
          src="/en_flag.svg"
          width="15%"
        />English</li>
    </NuxtLink>
    <NuxtLink :to="`/en` + $route.fullPath">
      <li><img
          class="v-mid"
          src="/vi_flag.svg"
          width="15%"
        />Tiếng Việt</li>
    </NuxtLink>
  </ul>
</template>
<style>
.languagepicker {
  display: inline-block;
  padding: 0;
  height: 40px;
  overflow: hidden;
  transition: all 0.3s ease;
  vertical-align: top;
}

.languagepicker:hover {
  /* don't forget the 1px border */
  height: 81px;
}

.languagepicker a {
  color: #000;
  text-decoration: none;
}

.languagepicker li {
  display: block !important;
  padding: 0px 20px !important;
  line-height: 40px;
  border-top: 1px solid #eee;
  text-align: left;
}

.languagepicker li:hover {
  background-color: #eee;
}

.languagepicker a:first-child li {
  border: none;
}

.languagepicker li img {
  margin-right: 5px;
}

.roundborders {
  border-radius: 5px;
}

.large:hover {
  /* 
	don't forget the 1px border!
	The first language is 40px heigh, 
	the others are 41px
	*/
  height: 245px;
}
</style>
