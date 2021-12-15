<template>
  <div>Dialog 示例</div>
  <h1>示例1</h1>
  <Button @click="toggle">toggle</Button>
  <Dialog v-model:visible="x" :close-on-click-overlay="false" :ok="f1" :cancel="f2">
    <template v-slot:title>
      <div>标题</div>
    </template>
    <template v-slot:content>
      <div>hi</div>
      <div>你好</div>
    </template>
  </Dialog>
  <h1>示例2</h1>
  <Button @click="showDialog">show</Button>
</template>
<script lang="ts">
import Dialog from '../lib/Dialog.vue'
import Button from '../lib/Button.vue';
import {ref} from 'vue';
import {openDialog} from '../lib/openDialog'
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
    const showDialog=()=>{
      openDialog({
        title:'标题2',
        content:'一些内容',
        ok(){
          console.log('ok');
        },
        cancel(){
          console.log('cancel');
        },
        closeOnClickOverlay:false
      })
    }
    return{x,toggle,f1,f2,showDialog}
  }
}
</script>

<style lang="scss" scoped>

</style>