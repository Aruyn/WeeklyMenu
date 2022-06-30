<template>
  <div class="weekday">
    <h1 class="weekdaycontent">{{ name }}</h1>
    <h1 class="weekdaycontent">⇨</h1>
    <suggestion class="weekdaycontent" :name="suggestion" />
    <button v-on:click="onSuggestPressed()">Foreslå for denne dagen</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Suggestion from "./Suggestion.vue";

export default defineComponent({
  components: { Suggestion },
  props: {
    name: String,
    suggestion: String,
  },
  methods:{
    onSuggestPressed(){
      this.$emit("suggestPressed");
    }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.weekday {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.weekdaycontent {
  margin: 1rem;
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
