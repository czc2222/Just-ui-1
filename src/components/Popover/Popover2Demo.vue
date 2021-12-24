<demo>
将触发方式改为 hover
</demo>
<template>
  <Popover trigger="hover">
    <Button>上方弹出</Button>
    <template v-slot:content>
      弹出内容
    </template>
  </Popover>
  <Popover position="bottom" trigger="hover">
    <Button>下方弹出</Button>
    <template v-slot:content>
      弹出内容
    </template>
  </Popover>
  <Popover position="left" trigger="hover">
    <Button>左边弹出</Button>
    <template v-slot:content>
      弹出内容
    </template>
  </Popover>
  <Popover position="right" trigger="hover">
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
