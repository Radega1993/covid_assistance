<template>
<div>
  <form class="login" @submit.prevent="login">
    <h1> Sing in</h1>
    <label> Email </label>
    <input required v-model="email" type="email" placeholder="Name"/>
    <label> Password </label>
    <input required v-model="password" type=password" placeholder="Password"/>
    <hr/>
    <button type="submit"> Login </button>
  </form>
</div
</template>

<script>
export default {
  data() {
    return {
      email : "",
      password : ""
    }
  },
  methods: {
    login: function () {
      let email = this.email
      let password = this.password
      this.$store.dispatch('login' {email, password})
      .then(() => this.$router.push('/'))
      .catch(err => console.log(err))
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
