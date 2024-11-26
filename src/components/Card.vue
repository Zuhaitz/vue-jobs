<script setup>
  defineProps({
    title: { type: String, default: "Base title" },
    description: {
      type: String,
      default: "Base description",
    },
    button: {
      type: String,
      default: "Button",
    },
    backgroundColor: {
      type: String,
      default: "bg-gray-100",
    },
    buttonColor: {
      type: String,
      default: "bg-black text-white hover:bg-gray-700",
    },
  });
</script>

<template>
  <div :class="['card p-6 rounded-lg shadow-md', backgroundColor]">
    <h2 class="text-2xl font-bold">{{ title }}</h2>
    <p class="mt-2 mb-4">{{ description }}</p>
    <a
      href="jobs.html"
      :class="['inline-block rounded-lg px-4 py-2', buttonColor]"
    >
      {{ button }}
    </a>
  </div>
</template>

<style scoped>
  @keyframes show {
    from {
      opacity: 0;
      /* scale: 50%; */
      transform: translateY(100px);
    }

    to {
      opacity: 1;
      /* scale: 100%; */
      transform: translateY(0);
    }
  }

  .card {
    animation: show 0.5s;
    transition: scale 0.3s;

    /* Scroll */
    /* view-timeline-name: --card;
    view-timeline-axis: block;

    animation-timeline: --card;
    animation-name: show;
    animation-range: entry 25% cover 50%;
    animation-fill-mode: both; */
  }

  .card:hover {
    scale: 102%;
  }

  .card > a {
    transition: scale 0.2s, color 0.2s, background-color 0.2s;
  }

  .card > a:hover {
    scale: 110%;
  }
</style>
