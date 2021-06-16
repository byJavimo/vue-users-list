<template>
  <ul class="users-list">
    <li v-for="user in users" :key="user.id">
        <UserItem v-bind:user="user" @removeUser="emitDeleteUser($event)"/>
    </li>
  </ul>
</template>

<script>
import UserItem from './UserItem.vue'
export default {
  name: 'UsersList',
  components: {
    UserItem
  },
  props: {
    users: Array
  },
  methods: {
    emitDeleteUser(id) {
      this.$emit('removeUser', id);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
  width: 100%;
}
</style>
