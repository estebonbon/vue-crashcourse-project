<script>
import { ref, onMounted } from 'vue';
  export default {
    setup() {
      const name = ref("John Doe");
      const status = ref("active");
      const tasks = ref(['Task one', 'Task two', 'Task three']);
      const link = "https://www.google.com";
      const newTask = ref('paper');

      const toggleStatus = () => {
        if (status.value === 'active') {
          status.value = 'inactive';
        } else if (status.value === 'inactive') {
          status.value = 'pending';
        } else {
          status.value = 'active';
        }
      };

      const addTask = () => {
        if (newTask.value.trim() !== '') {
          tasks.value.push(newTask.value);
          newTask.value = ''; // Clear the input field after adding the task
        }
      }

      const deleteTask = (index) => {
        tasks.value.splice(index, 1);
      };

      onMounted(async () => {
        try {
          const response = await fetch('https://jsonplaceholder.typicode.com/todos');
          const data = await response.json();
          tasks.value = data.map(task => task.title); // Assuming the API returns an array of tasks with a 'title' property
        } catch (error) {
          console.error('Error fetching tasks:', error);
        }
      })

      return {
        name,
        status,
        tasks,
        link,
        toggleStatus, 
        newTask,
        addTask,
        deleteTask,
      };
    }
  };

</script>
<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is Active</p>
  <p v-else-if="status === 'pending'">User Pending</p>
  <p v-else>User is Inactive</p>

  <form @submit.prevent="addTask">
    <label for="New Task">New Task</label>
    <!-- V-Model means keep the element and the variable in sync. If the variable changes, the element will change and vice versa.   -->
    <input type="text" id="newTask" name="newTask" v-model="newTask" /> 
    <button type="submit">Add Task</button> 
  </form> 
  <h3>Tasks:</h3>
  <ul>
    <li v-for="(task, index) in tasks" :key="task">
      <span>{{ task }}</span>
      <button @click="deleteTask(index)">x</button>
    </li>
  </ul>
  <a :href="link" target="_blank">Google</a>

  <br />
  <button @click="toggleStatus">Change Status</button>
</template>

<!-- <style scoped>
  h1 {
    color: red;
  }
</style> --> 