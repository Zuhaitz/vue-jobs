<script setup>
  import Card from "./Card.vue";
</script>

<template>
  <section class="py-4">
    <div class="m-auto lg:container">
      <div class="grid grid-cols-1 gap-4 p-4 rounded-lg md:grid-cols-2">
        <Card
          title="For Developers"
          description="Browse our Vue jobs and start your career today"
          button="Browse Jobs"
        />
        <Card
          title="For Employers"
          description="List your job to find the perfect developer for the role"
          button="Add Job"
          background-color="bg-green-100"
          button-color="bg-green-500 text-white hover:bg-green-600"
        />
      </div>
    </div>
  </section>
</template>
