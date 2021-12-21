<demo>
常规用法
</demo>
<template>
  <Button @click="toggle">打开对话框</Button>
  <Dialog v-model:visible="x" :close-on-click-overlay="false" :ok="f1" :cancel="f2">
    <template v-slot:title>
      <div>标题</div>
    </template>
    <template v-slot:content>
      <div>hi</div>
      <div>你好</div>
    </template>
  </Dialog>
</template>
<script lang="ts">
import Dialog from '../../lib/Dialog.vue'
import Button from '../../lib/Button.vue';
import {ref} from 'vue';
export default {
  components:{
    Button,
    Dialog,
  },
  setup(){
    const x=ref(false)
    const toggle =()=>{
      x.value = !x.value
    }
    const f1=()=>{
      return false
    }
    const f2 =()=>{

    }
    return{x,toggle,f1,f2}
  }
}
</script>
