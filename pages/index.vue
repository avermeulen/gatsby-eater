<template>
  <div class="container">
    <div>
      <h1>Order a gatsby</h1>
      <!-- <div>
			  Logged in:{{loggedIn}}
		  </div> -->
      <div v-if="!loggedIn">
        <input type="button" value="Login" v-on:click="login('andre')" />
      </div>

      <div v-if="loggedIn">
        <input type="button" value="Logout" v-on:click="logout()" />
        <gatsbys />
      </div>

      <div class="links"></div>
    </div>
  </div>
</template>

<script >
import { mapMutations } from "vuex";

export default {
  methods: {
    // login () {
    //   alert("!")
    // }

    ...mapMutations({
      login: "login",
      logout: "logout",
    }),
  },
  computed: {
    loggedIn(vm) {
      return vm.$store.state.loggedIn;
    },
  },
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
