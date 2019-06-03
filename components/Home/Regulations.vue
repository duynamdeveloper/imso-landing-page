<template>
  <section
    class="false bb b--black-10 flex flex-column flex-row-l items-stretch justify-stretch bg-gray"
    id="regulation"
  >
    <div class="pa4-ns flex w-50-l items-center content-start justify-center-ns justify-start false">
      <div class="pl5-l ph4-m pv2-ns pv4 ph3 w-60-m">
        <h3 class="f2-ns f4 mb3 lh-title ttu b red">{{ $t("home.regulations.title") }}</h3>
        <div
          class="f4 lh-copy mt0"
          v-html="$t('home.regulations.content')"
        ></div>
        <table
          class="f5-m f4-ns w-100 center mt4 mw8"
          cellspacing="0"
        >
          <thead>
            <tr class="stripe-dark">
              <th class="fw6 tl ttc pa3 bg-white black">Test</th>
              <th class="fw6 tl ttc pa3 bg-white black">{{$t("common.mathematics")}}</th>
              <th class="fw6 tl ttc pa3 bg-white black">{{$t("common.science")}}</th>
              <th class="fw6 tl ttc pa3 bg-white black">{{$t("common.duration")}}</th>
            </tr>
          </thead>
          <tbody class="lh-copy">
            <tr class="stripe-dark">
              <td class="pa3 ttc">test 1</td>
              <td class="pa3 ttc">{{$t("common.short_answer")}}</td>
              <td class="pa3 ttc">{{$t("common.theoretical")}} 1</td>
              <td class="pa3 ttc">60 {{$t("common.minutes")}}</td>
            </tr>
            <tr class="stripe-dark">
              <td class="pa3 ttc">Test 1</td>
              <td class="pa3 ttc">{{$t("common.essay")}}</td>
              <td class="pa3 ttc">{{$t("common.theoretical")}} 2</td>
              <td class="pa3 ttc">90 {{$t("common.minutes")}}</td>
            </tr>
            <tr class="stripe-dark">
              <td class="pa3 ttc">Test 1</td>
              <td class="pa3 ttc">{{$t("common.exploration")}}</td>
              <td class="pa3 ttc">{{$t("common.experiment")}} 1</td>
              <td class="pa3 ttc">120 {{$t("common.minutes")}}</td>
            </tr>

          </tbody>
        </table>
      </div>
    </div>
    <div class="flex w-50-l items-center justify-center false pa5-l pa4"><img
        class="luminous"
        alt="showing the status page of urlbox.io"
        src="/regulations_bg.jpg"
      >
    </div>
  </section>
</template>
