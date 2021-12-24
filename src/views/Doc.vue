<template>
  <div class="layout">
    <TopNav :toggle-menu-button-visible="true"  class="nav" />
    <div class="content">
      <aside v-if="asideVisible">
        <h3>入门</h3>
        <ol>
          <li>
            <router-link to="/doc/intro">介绍</router-link>
          </li>
          <li>
            <router-link to="/doc/install">YARN</router-link>
          </li>
          <li>
            <router-link to="/doc/install2">NPM</router-link>
          </li>
          <li>
            <router-link to="/doc/getStart">开始使用</router-link>
          </li>
        </ol>
        <h3>组件列表</h3>
        <ol>
          <li>
            <router-link to="/doc/button">Button 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/switch">Switch 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/tabs">Tabs 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/dialog">Dialog 组件</router-link>
          </li>
          <li>
            <router-link to="/doc/popover">Popover 组件</router-link>
          </li>
        </ol>
      </aside>
      <main>
        <router-view/>
      </main>
    </div>
  </div>
</template>

<script lang="ts">
import TopNav from "../components/TopNav.vue";
import {inject, Ref} from 'vue';
export default {
  components: {TopNav},
  setup(){
    const asideVisible = inject<Ref<boolean>>('asideVisible')
    return {asideVisible}
  }
}
</script>

<style lang="scss" scoped>
$aside-index:10;
.layout {
  display: flex;
  flex-direction: column;
  height: 100vh;
  > .nav {
    flex-shrink: 0;
    border-bottom: 1px solid #eaecef;
    padding-bottom: 16px;
    background: white;
  }
  > .content {
    flex-grow: 1;
    padding-top: 60px;
    padding-left: 156px;
    @media (max-width: 500px) {
      padding-left: 0;
    }
  }
}
.content {
  display: flex;

  > aside {
    flex-shrink: 0;
  }
  > main {
    flex-grow: 1;
    margin-top: 16px;
    padding: 16px;
    background: white;
    overflow: auto;
  }
}
aside {
  background: white;
  z-index: $aside-index;
  width: 150px;
  position: fixed;
  top: 0;
  left: 0;
  padding: 86px 0 16px 0;

  height: 100%;
  > h3 {
    margin-bottom: 4px;
    padding: 0 8px;
  }
  > ol {
    > li {

      > a{
        display: block;
        padding: 4px 16px;
        text-decoration: none;
        position: relative;
      }


      .router-link-active{
        background: white;
        color:#0170fe;

        &::before{
            position: absolute;
            width: 2px;
            content: '';
            height: 100%;
            background: #0170fe;
            margin: -4px  132px;


        }
      }
    }
  }
  main {
    overflow: auto;
  }
}
</style>