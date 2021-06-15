<template>
  <CreateUser msg="Welcome to Your Vue.js App"/>
  <UsersList></UsersList>
</template>

<script>
import CreateUser from './components/CreateUser.vue'
import UsersList from './components/UsersList.vue'


export default {
  name: 'App',
  components: {
    CreateUser,
    UsersList
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
  margin-top: 60px;
}
</style>
