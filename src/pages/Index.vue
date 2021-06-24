<template>
  <q-page class="flex flex-center">
    <div class="card" v-for="item in list" :key="item">{{item}}</div>
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
              'ㄢ','ㄣ','ㄤ','ㄥ','ㄦ','ㄧ','ㄨ','ㄩ']
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
  }
</style>