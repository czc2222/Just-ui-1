<demo>
支持 HTML
</demo>
<template>
  <Popover>
    <Button>上方弹出</Button>
    <template v-slot:content>
      弹出内容
    </template>
  </Popover>
  <Popover position="bottom">
    <Button>下方弹出</Button>
    <template v-slot:content>
      弹出内容
    </template>
  </Popover>
  <Popover position="left">
    <Button>左边弹出</Button>
    <template v-slot:content>
      弹出内容
    </template>
  </Popover>
  <Popover position="right">
    <Button>右边弹出</Button>
    <template v-slot:content>
      弹出内容
    </template>
  </Popover>
</template>
<script lang="ts">
import Popover from '../../lib/Popover.vue';
import Button from '../../lib/Button.vue';

export default {
  components: {Button, Popover}
};
</script>
