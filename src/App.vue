<template>
  <div class="app">
    <div class="pr">
      <h2>Prueba tecnica Clase Alpha</h2>
      <h2>Daniel Gonzalo Alzate Restrepo</h2>
    </div>
    <h1 class="titulo">Lista de Tareas</h1>
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

.titulo {
  text-align: center;
  color: rgb(37, 10, 133);
  font-size: xx-large;
  font-weight: 900;
  border-bottom: 1px solid rgb(111, 111, 105);
}

.pr {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  justify-content: center;
  gap: 1rem;
  margin-top: 2rem;
  text-align: center;
}

.pr h2 {
  font-size: small;
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
