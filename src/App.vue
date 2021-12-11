<template>
  <div>导航栏</div>
  <router-link to="/">frank</router-link> |
  <router-link to="/xxx">frank2</router-link>
  <hr>
  <router-view/>
</template>

<script>


export default {
  name: 'App',
  components: {

  }
}
</script>
