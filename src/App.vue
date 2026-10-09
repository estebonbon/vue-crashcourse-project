<script>
  export default {
    data() {
      return {
        name: "John Doe",
        status: "small",
        tasks: ['Task one', 'Task two', 'Task three'],
        link: 'https://www.google.com'
      }
    }
  };
</script>
<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is Active</p>
  <p v-else-if="status === 'pending'">User Pending</p>
  <p v-else>User is Inactive</p>

  <h3>Tasks:</h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>
  <a :href="link" target="_blank">Google</a>

  <br />
  <button v-on:click="toggleStatus">Change Status</button>
</template>

<!-- <style scoped>
  h1 {
    color: red;
  }
</style> --> 