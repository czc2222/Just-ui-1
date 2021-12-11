<template>
  <div>
    <router-view/>
  </div>
</template>

<script lang="ts">
import {provide, ref} from 'vue';
import {router} from './router';
export default {
  name: 'App',
  components: {},
  setup(){
    const width =document.documentElement.clientWidth //获取屏幕宽度
    const asideVisible = ref(width > 500)
    provide('asideVisible',asideVisible)
    router.afterEach(()=>{
      if(width <= 500){
        asideVisible.value = false
      }

    })
  }
}
</script>
