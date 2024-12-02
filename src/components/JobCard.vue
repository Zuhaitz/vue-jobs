<script setup>
  defineProps({ job: Object });
</script>

<template>
  <div
    class="grid grid-cols-1 gap-4 p-4 rounded-xl shadow-md relative bg-white"
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
        class="px-4 py-2 text-sm text-center rounded-lg text-white bg-green-500"
        >Read More</a
      >
    </div>
  </div>
</template>
