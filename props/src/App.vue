<script setup>
import { ref } from "vue";
import ListItem from "./components/ListItem.vue";

let database = ref([
  {
    name: "Jane",
    deparment: "Cricket",
    salary: 300000,
  },
  {
    name: "Stark",
    deparment: "Movies",
    salary: 400000,
  },
  {
    name: "John",
    deparment: "Engineering",
    salary: 30000,
  },
]);
function deleteCard(position) {
  database.value.splice(position, 1);
}
</script>

<template>
  <main>
    <ListItem 
    v-for="(item, index) in database"
    :name="item.name" 
    :department="item.deparment" 
    :salary="item.salary" 
    :position="index" 
    v-on:deleteItem="deleteCard"
    />
  </main>
</template>

<style scoped>
main {
  display: flex;
  justify-content: center;
  flex-direction: column;
}
</style>
