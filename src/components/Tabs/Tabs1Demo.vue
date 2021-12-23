<demo>
常规用法
</demo>
<template>
  <Tabs v-model:selected="x">
    <Tab title="导航1">导航1的内容</Tab>
    <Tab title="导航2">导航2的内容</Tab>
  </Tabs>
</template>

<script lang="ts">
import {Tab,Tabs} from '../../lib/index'

import {
  ref
} from 'vue'
export default {
  components: {
    Tabs,
    Tab
  },
  setup() {
    const x = ref('导航2')
    return {
      x
    }
  }
}
</script>