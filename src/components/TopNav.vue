<template>
  <div class="topnav">
    <router-link to="/" class="logo" >
      <svg class="icon">
        <use xlink:href="#icon-logo"></use>
      </svg>
      <h3>Just UI</h3>
    </router-link>
    <ul class="menu">
      <li>
        <router-link to="/">主页</router-link>
      </li>
      <li>
        <router-link to="/doc">文档</router-link>
      </li>

    </ul>
    <div class="github">
      <a href="https://github.com/czc2222/Just-ui-1">
        <svg>
          <use xlink:href="#icon-github"></use>
        </svg>
      </a>
    </div>
    <svg v-if="toggleMenuButtonVisible"
        class="toggleAside" @click="toggleMenu">
      <use xlink:href="#icon-menu"></use>
    </svg>
  </div>

</template>

<script lang="ts">
import {inject,Ref} from 'vue';

export default {
  props:{
    toggleMenuButtonVisible: {
      type: Boolean,
      default: false
    }
  },
  setup(){
    const asideVisible = inject<Ref<boolean>>('asideVisible')
    const toggleMenu=()=>{
      asideVisible.value = ! asideVisible.value
    }
    return {toggleMenu}
  },

}
</script>

<style lang="scss" scoped>
$color: black;
.topnav {
  color: $color;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 20;
  display: flex;
  padding: 0 16px;
  justify-content: center;
  align-items: center;
  > .logo {
    display: flex;
    justify-content: center;
    align-items: center;
    text-decoration: none;
    margin-right: auto;
    >svg {
      width: 32px;
      height: 32px;
    }
    > h3{
      padding-left: 8px;

    }

  }
  > .github {
    padding: 16px;
    > a{
      > svg{
        width: 26px;
        height: 26px;
      }
    }

  }
  > .menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;

    > li {
      padding: 16px 0;
      margin: 0 1em;
      &:hover{
        position: relative;
        color:#0170fe;
        > a::before{
          position: absolute;
          height: 2px;
          content: '';
          width: 100%;
          background: #0170fe;
          margin-top:-16px;
        }
      }

      > a{
        text-decoration: none;
      }
    }
  }
  > .toggleAside{
    display: none;
    width: 32px;
    height: 32px;
    position: absolute;
    left: 16px;
    top: 50%;
    transform: translateY(-50%);
  }
  @media (max-width:500px) {
    >.menu,.github{
      display: none;
    }
    >.logo{
      margin: 0 auto;
    }
    > .toggleAside{
      display: inline-block;

    }
  }
}
</style>