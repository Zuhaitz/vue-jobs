<script setup>
  import { ref } from "vue";
  import jobData from "../jobs.json";

  const jobs = ref(jobData);
</script>

<template>
  <section class="px-4 py-10 bg-blue-50">
    <div class="container-xl lg:container m-auto">
      <h2 class="mb-6 text-3xl font-bold text-center text-green-500">
        Browse Jobs
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div v-for="job in jobs" :key="job.id">
          {{ job.title }}
        </div>
      </div>
    </div>
  </section>
</template>
