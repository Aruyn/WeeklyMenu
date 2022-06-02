<template>
  <div class="menu">
    <WeekDay name="Mandag" suggestion="[Forslag]"/>
    <WeekDay name="Tirsdag" suggestion="[Forslag]"/>
    <WeekDay name="Onsdag" suggestion="[Forslag]"/>
    <WeekDay name="Torsdag" suggestion="[Forslag]"/>
    <WeekDay name="Fredag" suggestion="[Forslag]"/>
    <WeekDay name="Laurdag" suggestion="[Forslag]"/>
    <WeekDay name="Søndag" suggestion="[Forslag]"/>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import WeekDay from './WeekDay.vue';

@Options({
  props: {
    msg: String
  },
   components: {
    WeekDay
  },
})
export default class WeeklyMenu extends Vue {
  msg!: string
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
