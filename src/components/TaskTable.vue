<template>
  <div>
    <label for="filter">Filtrar:</label>
    <select id="filter" v-model="filter">
      <option value="all">Todas</option>
      <option value="completed">Completadas</option>
      <option value="pending">Pendientes</option>
    </select>

    <table>
      <thead>
        <tr>
          <th>Título</th>
          <th>Completada</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="task in filteredTasks" :key="task.id">
          <td>{{ task.title }}</td>
          <td><input type="checkbox" :checked="task.completed" disabled /></td>
        </tr>
      </tbody>
    </table>

    <p v-if="error" style="color: red">{{ error }}</p>
  </div>
</template>

<script setup>
import { ref, computed, onMounted } from "vue";

const tasks = ref([]);
const error = ref(null);
const filter = ref("all");

const filteredTasks = computed(() => {
  if (filter.value === "completed") {
    return tasks.value.filter((task) => task.completed);
  } else if (filter.value === "pending") {
    return tasks.value.filter((task) => !task.completed);
  }
  return tasks.value;
});

onMounted(async () => {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/todos");
    if (!response.ok) throw new Error("Error al obtener tareas");
    const data = await response.json();
    tasks.value = data.slice(0, 10);
  } catch (err) {
    // prettier-ignore
    error.value = 
    "No se pudo cargar la lista de tareas. Intenta nuevamente más tarde.";
  }
});
</script>
