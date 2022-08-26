<template>
  <div class="menu">
    <WeekDay name="Mandag" :suggestion="mondaySuggestion" @suggestPressed="SetSuggestion(1)" @lockPressed="SetLockPressed(1)" />
    <WeekDay name="Tirsdag" :suggestion="tuesdaySuggestion" @suggestPressed="SetSuggestion(2)" @lockPressed="SetLockPressed(2)"/>
    <WeekDay name="Onsdag" :suggestion="wednesdaySuggestion" @suggestPressed="SetSuggestion(3)" @lockPressed="SetLockPressed(3)"/>
    <WeekDay name="Torsdag" :suggestion="thursdaySuggestion" @suggestPressed="SetSuggestion(4)" @lockPressed="SetLockPressed(4)"/>
    <WeekDay name="Fredag" :suggestion="fridaySuggestion" @suggestPressed="SetSuggestion(5)" @lockPressed="SetLockPressed(5)"/>
    <WeekDay name="Laurdag" :suggestion="saturdaySuggestion" @suggestPressed="SetSuggestion(6)" @lockPressed="SetLockPressed(6)"/>
    <WeekDay name="Søndag" :suggestion="sundaySuggestion" @suggestPressed="SetSuggestion(7)" @lockPressed="SetLockPressed(7)"/>
    <button v-on:click="SetAllSuggestions()">Foreslå for alle dager</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import WeekDay from "./WeekDay.vue";

export default defineComponent({
  components: { WeekDay },
  data: function () {
    return {
      mondaySuggestion: "",
      tuesdaySuggestion: "",
      wednesdaySuggestion: "",
      thursdaySuggestion: "",
      fridaySuggestion: "",
      saturdaySuggestion: "",
      sundaySuggestion: "",
      mondayLocked: false,
      tuesdayLocked: false,
      wednesdayLocked: false,
      thursdayLocked: false,
      fridayLocked: false,
      saturdayLocked: false,
      sundayLocked: false,
      suggestions: [
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
        "Kjøttpudding",
      ],
    };
  },
  methods: {
    SetAllSuggestions() {
      if(!this.mondayLocked) this.mondaySuggestion = this.PickSuggestion();
      if(!this.tuesdayLocked) this.tuesdaySuggestion = this.PickSuggestion();
      if(!this.wednesdayLocked) this.wednesdaySuggestion = this.PickSuggestion();
      if(!this.thursdayLocked) this.thursdaySuggestion = this.PickSuggestion();
      if(!this.fridayLocked) this.fridaySuggestion = this.PickSuggestion();
      if(!this.saturdayLocked) this.saturdaySuggestion = this.PickSuggestion();
      if(!this.sundayLocked) this.sundaySuggestion = this.PickSuggestion();
    },
    SetLockPressed(n: number) {
      switch (n) {
        case 1:
          this.mondayLocked = !this.mondayLocked;
          break;
        case 2:
          this.tuesdayLocked = !this.tuesdayLocked;
          break;
        case 3:
          this.wednesdayLocked = !this.wednesdayLocked;
          break;
        case 4:
          this.thursdayLocked = !this.thursdayLocked;
          break;
        case 5:
          this.fridayLocked = !this.fridayLocked;
          break;
        case 6:
          this.saturdayLocked = !this.saturdayLocked;
          break;
        case 7:
          this.sundayLocked = !this.sundayLocked;
          break;
      }
    },
    SetSuggestion(n: number) {
      switch (n) {
        case 1:
          this.mondaySuggestion = this.PickSuggestion();
          break;
        case 2:
          this.tuesdaySuggestion = this.PickSuggestion();
          break;
        case 3:
          this.wednesdaySuggestion = this.PickSuggestion();
          break;
        case 4:
          this.thursdaySuggestion = this.PickSuggestion();
          break;
        case 5:
          this.fridaySuggestion = this.PickSuggestion();
          break;
        case 6:
          this.saturdaySuggestion = this.PickSuggestion();
          break;
        case 7:
          this.sundaySuggestion = this.PickSuggestion();
          break;
      }
    },
    PickSuggestion() {
      return this.suggestions[
        Math.floor(Math.random() * this.suggestions.length)
      ];
    },
  },
});
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
  box-shadow: 0 12px 16px 0 rgba(0, 0, 0, 0.24),
    0 17px 50px 0 rgba(0, 0, 0, 0.19);
}
</style>
