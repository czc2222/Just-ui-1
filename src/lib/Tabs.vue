<template>
  <div>
    <div v-for="(t,index) in title" :key="index">{{t}}</div>
    <component v-for="(c,index) in defaults" :is="c" :key="index"/>
  </div>
</template>
<script lang="ts">
import Tab from './Tab.vue';

export default {
  setup(props, context) {
    const defaults = context.slots.default();

    defaults.forEach((tag) => {
          if (tag.type !== Tab) {
            throw new Error('Tabs的子标签必须是Tab');
          }
        }
    );
    const title= defaults.map(tag=>{
      return tag.props.title
    })
    return {defaults,title};
  }
};
</script>

<style lang="scss">

</style>