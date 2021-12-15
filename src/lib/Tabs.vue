<template>
  <div class="gulu-tabs">
    <div class="gulu-tabs-nav">
      <div class="gulu-tabs-nav-item"
           v-for="(t,index) in titles" :key="index"
           :class="{selected:t === selected}"
           @click="select(t)"
           :ref="el=>{if(el) navItems[index] =el}"
      >{{t}}</div>
      <div class="gulu-tabs-nav-indicator" ref="indicator"></div>
    </div>
    <div class="gulu-tabs-content">
      <component class="gulu-tabs-content-item"
                 v-for="(c,index) in defaults"
                 :is="c" :key="index"
                 :class="{selected:c.props.title === selected}"
                 />
    </div>
  </div>
</template>
<script lang="ts">
import Tab from './Tab.vue';
import {onMounted, ref} from 'vue';


export default {
  props:{
    selected:{
      type:String
    }
  },
  setup(props, context) {
    const navItems =ref<HTMLDivElement[]>([])
    const indicator =ref<HTMLDivElement>(null)
    onMounted(()=>{ //挂载之后
      const divs =navItems.value
      const result =divs.filter(div=>div.classList.contains('selected'))[0]  //获取被选中的class
      const {width}=result.getBoundingClientRect() //获取被选中的div的宽度
      indicator.value.style.width = width + 'px'
    })
    const defaults = context.slots.default();

    defaults.forEach((tag) => {
          if (tag.type !== Tab) {
            throw new Error('Tabs的子标签必须是Tab');
          }
        }
    );
    const titles= defaults.map(tag=>{
      return tag.props.title
    })
    const select =(title:string)=>{
      context.emit('update:selected',title)
    }

    return {defaults,titles,select,navItems,indicator};
  }
};
</script>

<style lang="scss">
$blue: #40a9ff;
$color: #333;
$border-color: #d9d9d9;
.gulu-tabs {
  &-nav {
    display: flex;
    color: $color;
    border-bottom: 1px solid $border-color;
    position: relative;
    &-item {
      padding: 8px 0;
      margin: 0 16px;
      cursor: pointer;

      &:first-child {
        margin-left: 0;
      }
      &.selected {
        color: $blue;
      }
    }
    &-indicator {
      position: absolute;
      height: 3px;
      background: $blue;
      left: 0;
      bottom: -1px;
      width: 100px;
    }
  }
  &-content {
    padding: 8px 0;

    &-item{
      display: none;
      &.selected{
        display: block;
      }
    }

  }

}
</style>