<template>
  <form class="create-user">
    <div class="name-input">
      <label> Nombre </label>
      <input type="text" v-model="name">
    </div>
    <div class="surname-input">
      <label>Apellidos</label>
      <input type="text" v-model="surname">
    </div>
    <button class="submit-input" type="submit" @click="emitNewUser($event)"> Añadir usuario </button>
  </form>
</template>

<script>

export default {
  name: 'CreateUser',
  data: () => {
    return {
      name: '',
      surname: ''
    }
  },
  methods: {
    emitNewUser(ev) {
      ev.preventDefault();
      if (this.name && this.surname) {
        this.$emit('newUser', {
          name: this.name,
          surname: this.surname
        });
        this.name = '';
        this.surname = '';
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .create-user {
    display: flex;
    flex-direction: row;
    width: 20%;
    margin: 0 auto;
  }
  .name-input, .surname-input, .submit-input {
    margin: 20px;
  }
</style>
