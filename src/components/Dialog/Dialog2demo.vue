<demo>
一键打开 Dialog
</demo>
<template>
  <Button @click="showDialog">打开对话框</Button>
</template>
<script lang="ts">
import {openDialog,Button} from '../../lib/index'
import {
  ref,
  h
} from 'vue'
export default {
  components:{
    Button,

  },
  setup(){
    const showDialog=()=>{
      openDialog({
        title: h('strong', {}, '标题'),
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
    return{showDialog}
  }
}
</script>

