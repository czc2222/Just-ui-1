<template>
  <div>
    <h1>Popover 示例</h1>
    <Demo :component="Popover1Demo" />

  </div>

</template>
<script lang="ts">
import Popover1Demo from './Popover/Popover1Demo.vue';
import Popover2Demo from './Popover/Popover2Demo.vue';
import Demo from './Demo.vue';

export default {
  components: {
    Demo
  },
  setup(){
    return{Popover1Demo,Popover2Demo}
  }

};
</script>
<style lang="scss" scoped>
$border-color: #d9d9d9;
.declare{
  border: 1px solid $border-color;
}
</style>
