<template>
  <div>
    <h1>Button 示例</h1>
    <Demo :component="Button1Demo" />、
    <Demo :component="Button2Demo" />
    <Demo :component="Button3Demo" />
    <Demo :component="Button4Demo" />
    <Demo :component="Button5Demo" />
  </div>

</template>
<script lang="ts">
import Button1Demo from './Button/Button1Demo.vue';
import Button2Demo from './Button/Button2Demo.vue';
import Button3Demo from './Button/Button3Demo.vue';
import Button4Demo from './Button/Button4Demo.vue';
import Button5Demo from './Button/Button5Demo.vue';
import Demo from './Demo.vue';

export default {
  components: {
    Demo
  },
  setup(){
    return{Button1Demo,Button2Demo,Button3Demo,Button4Demo,Button5Demo}
  }

};
</script>
