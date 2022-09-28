<template>
  <div>
    <form @submit.prevent="getFormData">
      <input
        type="text"
        placeholder="Description..."
        v-model="state.description"
      />
      <input type="number" placeholder="Prix..." v-model="state.value" />
      <input type="date" placeholder="Date..." v-model="state.date" />
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from "vue";

export default defineComponent({
  name: "FormComponent",
  setup(props, context) {
    const state = reactive({
      description: null,
      value: null,
      date: null,
    });
    function getFormData() {
      context.emit("get-form-data", {
        description: state.description,
        prix: state.value,
        date: state.date,
      });
    }
    return { state, getFormData };
  },
});
</script>

<style scoped></style>
