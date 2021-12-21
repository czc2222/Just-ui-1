<template>
  <h1>Tabs 示例</h1>
  <Demo :component="Tabs1Demo" />
</template>
<script lang="ts">
import Demo from './Demo.vue'
import Tabs1Demo from './Tabs/Tabs1Demo.vue';
export default {
  components:{
    Demo
  },
  setup(){
    return{Tabs1Demo}
  }
}
</script>

