<template>
  <div>
    <header-tracker :getTotalIncome="totalIncome" />
    <form-component @get-form-data="pushData" />
    <ListComponent :getShoppingList="shoppingList" />
  </div>
</template>

<script lang="ts">
import FormComponent from "/src/components/FormComponent.vue";
import HeaderTracker from "../components/HeaderTracker.vue";
import ListComponent from "@/components/ListComponent.vue";
import { computed, defineComponent, ref } from "vue";

export default defineComponent({
  name: "IncomeTracker",
  setup() {
    const shoppingList = ref([]);
    const totalIncome = ref(
      computed(() => {
        let total = 0;
        if (shoppingList.value.length > 0) {
          for (const element of shoppingList.value) {
            total += element.prix;
          }
        }

        return total;
      })
    );
    // eslint-disable-next-line
    function pushData(event: any) {
      shoppingList.value.push(event);
    }
    return { totalIncome, shoppingList, pushData };
  },
  components: { ListComponent, HeaderTracker, FormComponent },
});
</script>

<style scoped></style>
