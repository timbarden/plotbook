<template>
  <header class="header">
    <div class="header__user" v-if="$auth.isAuthenticated">
      <img :src="$auth.user.picture" />
      <div>
        <h2>{{ $auth.user.nickname }}</h2>
      </div>
    </div>
    <div class="header__btns">
      <div v-if="!$auth.loading">
        <div v-if="!$auth.isAuthenticated">
          <router-link to="/dashboard/">Log In</router-link>
        </div>
        <button v-if="$auth.isAuthenticated" @click="logout">Log out</button>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  methods: {
    // Log the user in
    login() {
      this.$auth.loginWithRedirect();
    },
    // Log the user out
    logout() {
      this.$auth.logout({
        returnTo: window.location.origin,
      });
    },
  },
};
</script>

<style lang="scss">
.header {
  color: #fff;
  background: rgba(#000, 0.8);
  padding: 0.75em 4vw;
  position: sticky;
  top: 0;
  z-index: 1;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  &__user {
    display: flex;
    align-items: center;
    padding-right: 1em;
    img {
      max-width: 2.5em;
      border-radius: 5px;
      margin: auto 1em auto 0;
    }
    h2 {
      font-size: 1.25em;
    }
    p {
      margin: 0;
      opacity: 0.5;
      font-size: 0.85em;
    }
  }
  &__btns {
    flex-shrink: 0;
    margin-left: auto;
  }
}
</style>
