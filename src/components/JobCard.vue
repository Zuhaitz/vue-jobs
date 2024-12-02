<script setup>
  defineProps({ job: Object });
</script>

<template>
  <div
    class="card grid grid-cols-1 gap-4 p-4 rounded-xl shadow-md relative bg-white"
  >
    <div>
      <p class="my-2 text-gray-600">{{ job.type }}</p>
      <h3 class="truncate text-xl font-bold">{{ job.title }}</h3>
    </div>

    <p class="md:max-h-[240px] md:h-[240px] text-ellipsis overflow-y-auto">
      {{ job.description }}
    </p>

    <p class="mb-2 text-green-500">{{ job.salary }}</p>

    <div class="border-t border-gray-200"></div>

    <div class="flex flex-col lg:flex-row lg:items-center justify-between">
      <div class="mb-3 lg:mb-0 text-orange-700">{{ job.location }}</div>
      <a
        :href="'/job/' + job.id"
        class="button px-4 py-2 text-sm text-center rounded-lg text-white bg-green-500"
        >Read More</a
      >
    </div>
  </div>
</template>

<style scoped>
  @keyframes show {
    from {
      transform: translateY(100px);
      opacity: 0;
    }

    to {
      transform: translateY(0);
      opacity: 1;
    }
  }

  .card {
    opacity: 0;
    animation: show ease-in;
    animation-timeline: view();
    animation-range: entry 20% cover 35%;
    animation-fill-mode: both;
  }

  .button {
    transition: scale 0.5s;
  }

  .button:hover {
    scale: 103%;
  }

  @media (min-width: 768px) {
    @keyframes show {
      from {
        transform: translateY(100px) rotate(10deg);
        opacity: 0;
      }

      to {
        transform: translateY(0) rotate(0);
        opacity: 1;
      }
    }

    .card {
      animation: show 0.6s ease;
      transition: all 0.5s;
      animation-fill-mode: forwards;
    }
  }
</style>
