<template>
  <div>
  <Header />
  <Main />
  </div>
</template>

<style>
*{
  padding: 0;
  margin: 0;
  border: none;
  text-decoration: none;
  outline: none;
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
}
</style>

<script>
import Header from '../components/Header.vue';
import Main from '../components/Main.vue';

export default {
  name: 'IndexPage',
  components: {
    Header,
    Main,
  },
  props: {
    name: {
      type: String,
      default: 'John Doe'
    }
  }
}
</script>
