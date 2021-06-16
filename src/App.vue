<template>
  <CreateUser class="create-user" @newUser="createUser($event)"/>
  <UsersList class="users-list" v-bind:users="users" @removeUser="deleteUser($event)"/>
</template>

<script>
import CreateUser from './components/CreateUser.vue'
import UsersList from './components/UsersList.vue'


export default {
  name: 'App',
  components: {
    CreateUser,
    UsersList
  },
  data: () => {
    return {
      users: [
        {
          id: 0,
          name: 'Pepito',
          surname: 'Flores'
        },
        {
          id: 1,
          name: 'Miguel',
          surname: 'De Cervantes'
        },
        {
          id: 2,
          name: 'Federico',
          surname: 'Garcia Lorca'
        }
      ]  
    }
  },
  methods: {
    createUser(ev) {
      this.users.push({
        id: this.users.length,
        name: ev.name,
        surname: ev.surname
      })
    },
    deleteUser(id) {
      this.users = this.users.filter(user => user.id !== id);
      console.log(this.users);
    }
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
  margin: 60px auto;
  display: flex;
  flex-direction: column;
  width: 100%
}

</style>
