<template>
  <q-page class="flex flex-center">
    <div class="card" v-for="item in items" :key="item.t" @click="item.focus=!item.focus">
      <h3>{{item.t}}</h3>
      <p v-show="item.focus">{{item.d}}</p>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageIndex',
  data() {
    return {
      list: ['ㄅ','ㄆ','ㄇ','ㄈ','ㄉ','ㄊ','ㄋ','ㄌ', 
              'ㄍ','ㄎ','ㄏ','ㄐ','ㄑ','ㄒ',
              'ㄓ','彳','ㄕ','ㄖ','ㄗ','ㄘ','厶',
              'ㄚ','ㄛ','ㄜ','ㄝ','ㄞ','ㄟ','ㄠ','ㄡ',
              'ㄢ','ㄣ','ㄤ','ㄥ','ㄦ','ㄧ','ㄨ','ㄩ'],
      items: [
        { t:'ㄅ', focus: false, d: '「包」之古字，說文解字：「勹，裹也，象人曲行，有所包裹。」，讀「ㄅㄠ」 取其「ㄅ」聲' },
        { t:'ㄆ', focus: false, d:'說文解字：「攵，小擊也。」即手執竿輕敲，讀「ㄆㄨ」(撲) 取其「ㄆ」聲'},
        { t:'ㄇ', focus: false, d: '“冪"的本字。遮蔽覆蓋之意，古音「ㄇㄧˋ」 取其「ㄇ」聲'},
        { t:'ㄈ', focus: false, d: '說文解字：「匚，受物之器。」古代一種盛物的器具，讀「ㄈㄤ」(方) 取其「ㄈ」聲'},
        { t:'ㄉ', focus: false, d: '古之「刀」字，讀「ㄉㄠ」 取其「ㄉ」聲' },
        { t:'ㄊ', focus: false, d: '古之「突」或「凸」，讀「ㄊㄨ」 取其「ㄊ」聲'},
        { t:'ㄋ', focus: false, d: '古之「乃」字，讀「ㄋㄞˇ」 取其「ㄋ」聲'},
        { t:'ㄌ', focus: false, d: '古之「力」字，讀「ㄌㄧˋ」 取其「ㄌ」聲'},
        { t:'ㄍ', focus: false, d: '說文解字：「巜，水流澮澮也。」川之小者，田間的水道，讀「ㄍㄨㄥ」(工) 取其「ㄍ」聲'},
        {t: 'ㄎ', focus: false, d: '說文解字：「丂，氣欲舒出，勹上礙於一也。」氣受阻礙而無法舒出或行而不利，讀「ㄎㄠˇ」(考) 取其「ㄎ」聲'},
        {t: 'ㄏ', focus: false, d: '古之「ㄏ」字，山側避風雨之居處，讀「ㄏㄢˇ」(罕) 取其「ㄏ」聲'},
        {t: 'ㄐ', focus: false, d: '古之「糾」字，說文解字：「丩，相糾繚也。」，讀「ㄐㄧㄡ」 取其「ㄐ」聲'},
        {t: 'ㄑ', focus: false, d: 'ㄑ：水小流。同"畎”、田間溝渠。讀「ㄑㄩㄢˇ」(犬) 取其「ㄑ」聲'},
        {t: 'ㄒ', focus: false, d: '古之「下」字，讀「ㄒㄧㄚˋ」 取其「ㄒ」聲'},
        {t: 'ㄓ', focus: false, d: '古之「之」字，讀「ㄓ」 取其「ㄓ」聲'},
        {t: 'ㄔ', focus: false, d: '明．張自烈．正字通：「左步為彳，右步為亍，合彳亍為行。」 彳：左腳的步伐。讀「ㄔ」 (吃) 取其「ㄔ」聲'},
        {t: 'ㄕ', focus: false, d: '古之「尸」字，讀「ㄕ」 取其「ㄕ」聲'},
        {t: 'ㄖ', focus: false, d: '古之「日」字(象形)，讀「ㄖ」 取其「ㄖ」聲'},
        {t: 'ㄗ', focus: false, d: '古之「節」字，讀作「ㄗ」音（分尖團）。讀如(早)之聲 取其「ㄗ」聲'},
        {t: 'ㄘ', focus: false, d: '古之「七」字，讀作「ㄘ」音（分尖團）。讀如(草)之聲 取其「ㄘ」聲'},
        {t: 'ㄙ', focus: false, d: '古之「私」字，讀「ㄙ」 取其「ㄙ」聲'},
        {t: 'ㄚ', focus: false, d: '古之「ㄚ」字，廣韻：「丫，象物開之形。」物之歧頭曰「ㄚ」，讀「ㄧㄚ」 (押) 取其「ㄚ」韻'},
        {t: 'ㄛ', focus: false, d: '古之「呵」字，說文解字：「ㄛ，反丂也。」。讀如(或)之韻 取其「ㄛ」韻'},
        {t: 'ㄜ', focus: false, d: '「ㄛ」之轉化，由"ㄛ"添筆而成（近代語音以及大多數方言o e不分）。讀如(峨)之韻'},
        {t: 'ㄝ', focus: false, d: '古之「也」字，讀「ㄧㄝˇ」 取其「ㄝ」韻'},
        {t: 'ㄞ', focus: false, d: '古之「亥」字，讀「ㄏㄞˋ」 取其「ㄞ」韻'}, 
        {t: 'ㄟ', focus: false, d: '「流」也，讀「ㄨㄟ」(威) 取其「ㄟ」韻'},
        {t: 'ㄠ', focus: false, d: '說文解字：「幺，小也。」“么"的本字。小也，細也。讀「ㄧㄠ」 取其「ㄠ」韻'},
        {t: 'ㄡ', focus: false, d: '握於手之象形字，讀「ㄧㄡˋ」(又) 取其「ㄡ」韻'},
        {t: 'ㄢ', focus: false, d: '說文解字：「ㄢ。艸木之華未發然」。花苞之象形，其意「含」也。讀「ㄏㄢˊ」 取其「ㄢ」韻'},
        {t: 'ㄣ', focus: false, d: '古之「隱」字，又作"乚”：匿也。讀「ㄧㄣˇ」 取其「ㄣ」韻'},
        {t: 'ㄤ', focus: false, d: '玉篇．尢部：「尢，跛、曲脛也。」腳跛也，讀「ㄤ」(骯)'}, 
        {t: 'ㄥ', focus: false, d: '說文解字段玉裁注：「ㄥ，古文厷，象形，象曲肱。」。厷讀「ㄍㄨㄥ」(供) 取其「ㄥ」韻'},
        {t: 'ㄦ', focus: false, d: '“兒"的簡化字。讀「ㄦˊ」'},
        {t: 'ㄧ', focus: false, d: '「一」是數字之始，讀「ㄧ」'},
        {t: 'ㄨ', focus: false, d: '古之「五」字，讀「ㄨˇ」'},
        {t: 'ㄩ', focus: false, d: '說文解字：「凵，飯器，以柳作之。」古盛飯之器，讀「ㄩ」(淤)'}
      ]
    }
  }
})
</script>

<style type="text/css" scoped="">
  
  .card {
    width: 160px;
    height: 220px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    border: 1px solid black;
    font-size: 26px;
    cursor: pointer;
  }

  p {
    font-size: 9px;
  }
</style>