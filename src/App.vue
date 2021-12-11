<template>
  <div>
    <router-view/>
  </div>
</template>

<script lang="ts">
import {provide, ref} from 'vue';
export default {
  name: 'App',
  components: {},
  setup(){
    const width =document.documentElement.clientWidth //获取屏幕宽度
    const asideVisible = ref(width <= 500 ? false : true)
    provide('asideVisible',asideVisible)
  }
}
</script>
