<template>
  <div class="app">
    <h1>Lista de Tareas</h1>
    <TaskTable />
  </div>
</template>

<script setup>
import TaskTable from "./components/TaskTable.vue";
</script>

<style>
body {
  font-family: Arial, sans-serif;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 1rem;
}

th {
  border: 1px solid #ccc;
  padding: 0.5rem;
  text-align: left;
}

td {
  border: 1px solid #ccc;
  padding: 0.5rem;
  text-align: left;
}
</style>
