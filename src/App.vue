<template>
  <div id="app">
    <Login v-if="!isUserLogged" @success="userLogged" />
    <UserDetails v-else :user="user" />
  </div>
</template>

<script>
import Login from '@/components/Login.vue'
import UserDetails from '@/components/UserDetails.vue'

export default {
  name: 'App',

  data() {
    return {
      isUserLogged: false,
      user: {},
    }
  },

  methods: {
    userLogged(user) {
      this.isUserLogged = true
      this.user = user
    },
  },

  components: {
    Login,
    UserDetails,
  },
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.input {
  padding: 0.6rem;
  margin-bottom: 1rem;
  width: 200px;
}
</style>
