<script>
  export default {
    data() {
      return {
        name: "John Doe",
        status: "small",
        tasks: ['Task one', 'Task two', 'Task three'],
        link: 'https://www.google.com'
      }
    },
    methods: {
      toggleStatus() {
        if (this.status === 'active') {
          this.status = 'inactive';
        } else if (this.status === 'inactive') {
          this.status = 'pending';
        } else {
          this.status = 'active';
        }
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
  <button @click="toggleStatus">Change Status</button>
</template>

<!-- <style scoped>
  h1 {
    color: red;
  }
</style> --> 