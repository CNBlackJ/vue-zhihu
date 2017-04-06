<template>
  <div class="login">
    <h1>{{ users }}</h1>
    <input type="text" v-model="username">
    <button v-on:click="addUser">AddUser</button>
  </div>
</template>

<script>
export default {
  name: 'login',
  data () {
    return {
      username: 'a',
      users: []
    }
  },
  methods: {
    addUser: function () {
      this.users.push(this.username)
    }
  }
}
</script>
