<template>
  <Switch :value="y" @input="y= $event"/>
</template>
<script lang="ts">
import Switch from '../lib/Switch.vue'
import {ref} from 'vue';
export default {
  setup(){
    const y = ref(false)
    return{y}
  },
   components:{
     Switch,
   }
}
</script>

<style lang="scss" scoped>

</style>