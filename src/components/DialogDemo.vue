<template>
  <h1>Dialog 示例</h1>
   <Demo :component="Dialog1demo"/>
   <Demo :component="Dialog2demo"/>
</template>
<script lang="ts">

import Demo from './Demo.vue';
import Dialog1demo from './Dialog/Dialog1demo.vue';
import Dialog2demo from './Dialog/Dialog2demo.vue';
export default {
  components:{
    Demo,
  },
  setup(){
    return{Dialog1demo,Dialog2demo}
  }
}
</script>

