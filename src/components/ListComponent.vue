<template>
  <div>
    <h1>LISTE D'ACHATS</h1>
    <div v-for="element in getShoppingList" :key="element">
      <list-element-component :listElement="element" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ListElementComponent from "@/components/ListElementComponent.vue";

export default defineComponent({
  components: { ListElementComponent },
  props: { getShoppingList: Array },
  name: "ListComponent",
});
</script>

<style scoped></style>
