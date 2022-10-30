<template>
  <UserVue/>
</template>

<script>
import HomeView from '@/views/HomeView.vue'
import UserVue from '@/views/UserView.vue'

export default {
    name: 'UserInfo',
    components: {
      HomeView,
      UserVue
    }
}
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
