<script setup>
    import Card from '@/components/Card.vue';
</script>

<template>
    <section class="py-4">
      <div class="container-xl lg:container m-auto">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 p-4 rounded-lg">
          <Card>
            <h2 class="text-2xl font-bold">For Developers</h2>
            <p class="mt-2 mb-4">
              Browse our Vue jobs and start your career today
            </p>
            <a
              href="jobs.html"
              class="inline-block bg-black text-white rounded-lg px-4 py-2 hover:bg-gray-700"
            >
              Browse Jobs
            </a>
          </Card> <!-- The cards used to be Divs and know we are using a component called Card. The Card component is a reusable component that can be used to create cards with different background colors. 
          The bg prop is used to set the background color of the card. The default value for the bg prop is 'bg-gray-100', but we can pass in a different value to change the background color of the card. 
          In this case, we are passing in 'bg-green-100' to change the background color of the second card to green. -->
          <Card bg="bg-green-100">
            <h2 class="text-2xl font-bold">For Employers</h2>
            <p class="mt-2 mb-4">
              List your job to find the perfect developer for the role
            </p>
            <a
              href="add-job.html"
              class="inline-block bg-green-500 text-white rounded-lg px-4 py-2 hover:bg-green-600"
            >
              Add Job
            </a>
          </Card>
        </div>
      </div>
    </section>

</template>