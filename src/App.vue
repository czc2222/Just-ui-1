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
    const asideVisible = ref(false)
    provide('asideVisible',asideVisible)
  }
}
</script>
