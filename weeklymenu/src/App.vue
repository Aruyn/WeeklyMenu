<template>
  <img alt="Vue logo" src="./assets/menu.png">
  <WeeklyMenu/>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import WeeklyMenu from './components/WeeklyMenu.vue';

@Options({
  components: {
    WeeklyMenu,
  },
})
export default class App extends Vue {}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
