<template>
  <div class="weekday">
    <h1 class="weekdaycontent">{{ name }}</h1>
    <h1 class="weekdaycontent">⇨</h1>
    <suggestion class="weekdaycontent" :name="suggestion" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Suggestion from './Suggestion.vue';

export default defineComponent({
  components: { Suggestion },
  props: {
    name: String,
    suggestion: String}
})
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.weekday{
  display:flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.weekdaycontent{
  margin: 1rem;
}
</style>
