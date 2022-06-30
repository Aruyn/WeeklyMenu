<template>
  <div class="menu">
    <WeekDay name="Mandag" :suggestion="mondaySuggestion"/>
    <WeekDay name="Tirsdag" :suggestion="tuesdaySuggestion"/>
    <WeekDay name="Onsdag" :suggestion="wednesdaySuggestion"/>
    <WeekDay name="Torsdag" :suggestion="thursdaySuggestion"/>
    <WeekDay name="Fredag" :suggestion="fridaySuggestion"/>
    <WeekDay name="Laurdag" :suggestion="saturdaySuggestion"/>
    <WeekDay name="Søndag" :suggestion="sundaySuggestion"/>
    <button v-on:click="SetAllSuggestions()">Foreslå for alle dager</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import WeekDay from './WeekDay.vue';

export default defineComponent({
  components: { WeekDay },
  data: function() {
    return{
    mondaySuggestion: "",
    tuesdaySuggestion: "",
    wednesdaySuggestion: "",
    thursdaySuggestion: "",
    fridaySuggestion: "",
    saturdaySuggestion: "",
    sundaySuggestion: "",
    suggestions:[
      "Pizza",
      "Spagetti",
      "Torsk",
      "Kjøttkake",
      "Taco",
      "Fiskepinner",
      "Fiskekake",
      "Nachos",
      "Pasta Carbonara",
      "Kotteletter",
      "Lasagne",
      "Hamburger",
      "Karbonader",
      "Pølse i brød",
      "Pølse m/pommes frittes",
      "Kjøttpudding"
    ]
    }
  },
  methods: {
    SetAllSuggestions(){
      this.mondaySuggestion = this.PickSuggestion();
      this.tuesdaySuggestion = this.PickSuggestion();
      this.wednesdaySuggestion = this.PickSuggestion();
      this.thursdaySuggestion = this.PickSuggestion();
      this.fridaySuggestion = this.PickSuggestion();
      this.saturdaySuggestion = this.PickSuggestion();
      this.sundaySuggestion = this.PickSuggestion();
    },
    PickSuggestion(){
    return this.suggestions[Math.floor(Math.random() * this.suggestions.length)]
    }
  }
})
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

button {
  padding: 16px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  transition-duration: 0.4s;
  cursor: pointer;
  background-color: white;
  color: black;
  border: 2px solid #9b9797;
  border-radius: 8px;
}

button:hover {
  background-color: #9b9797;
  color: white;
    box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24), 0 17px 50px 0 rgba(0,0,0,0.19);
}
</style>
