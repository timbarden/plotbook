<template>
  <div id="app">
    <Header />
    <router-view />
  </div>
</template>

<script>
import Header from "./components/Header";

export default {
  data() {
    return {
      title: process.env.VUE_APP_TITLE,
    };
  },
  components: {
    Header,
  },
  methods: {},
};
</script>

<style lang="scss">
@import "@/styles/base.scss";
* {
  box-sizing: border-box;
}
body {
  margin: 0;
  color: #333;
  background: #fff;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font: 400 1em/1.2 "Nunito", sans-serif;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  margin: 0;
}
#app {
  padding: 0;
}
h1 {
  font: 600 3.5em/1.2 "Caveat", sans-serif;
}
.header__btns a {
  display: inline-block;
  vertical-align: middle;
  text-decoration: none;
}
.header__btns a,
button {
  @extend %btn_reset;
  color: #333;
  border-radius: 5px;
  padding: 0.45em 0.7em;
  background: #eee;
  transition: background 0.1s ease;
  &.btn--sq {
    width: 2em;
    height: 2em;
    padding: 0;
    &:hover {
      background: #ddd;
    }
  }
  img {
    width: 1.25em;
    height: 1.25em;
  }
}
</style>
