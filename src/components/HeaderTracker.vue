<template>
  <div class="wrapper">
    <h1>TOTAL DES ACHATS</h1>
    <div>{{ getTotalIncome }} €</div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: { getTotalIncome: Number },
  name: "HeaderTracker",
});
</script>

<style scoped>
.wrapper {
  display: flex;
  justify-content: space-around;
  align-items: center;
}
</style>
