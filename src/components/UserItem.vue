<template>
  <div class="user-item">
    <div class="user-item__name"> {{user.name}} </div>
    <div class="user-item__surname"> {{user.surname}}</div>
    <div class="user-item__delete">
      <button @click="emitRemoveUser(user.id)">Eliminar</button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'UserItem',
  props: {
    user: {
      id: Number,
      name: String,
      surname: String
    }
  },
  methods: {
    emitRemoveUser(ev) {
      this.$emit('removeUser', ev);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .user-item {
    display: flex;
  }

  .user-item__name {
    flex: 1;
    padding: 20px
  }
  .user-item__surname {
    flex: 1;
    padding: 20px
  }
  .user-item__delete {
    flex: 1;
    padding: 20px;
  }
</style>
