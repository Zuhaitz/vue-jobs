<script setup>
  import { ref } from "vue";
  import jobData from "../jobs.json";
  import JobCard from "./JobCard.vue";

  defineProps({ limit: Number, showButton: { type: Boolean, default: false } });

  const jobs = ref(jobData);
</script>

<template>
  <section class="jobs-list px-4 py-10 bg-blue-50">
    <div class="container-xl lg:container m-auto">
      <h2 class="mb-6 text-3xl font-bold text-center text-green-500">
        Browse Jobs
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <JobCard
          v-for="job in jobs.slice(0, limit || jobs.length)"
          :key="job.id"
          :job="job"
        />
      </div>
    </div>
  </section>

  <section v-if="showButton" class="m-auto max-w-lg my-10 px-6">
    <a
      href="/jobs"
      class="block bg-black text-white text-center py-4 px-6 rounded-xl hover:bg-gray-700"
      >View All Jobs</a
    >
  </section>
</template>

<style scoped>
  @media (min-width: 768px) {
    .jobs-list .card:nth-child(2) {
      animation-delay: 0.2s;
    }
    .jobs-list .card:nth-child(3) {
      animation-delay: 0.4s;
    }
  }
</style>
