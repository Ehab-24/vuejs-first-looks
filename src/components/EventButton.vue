<script>
export default {
  props: {
    text: {
      type: String,
      default: "button",
    },
    event: {
      type: String,
    },
  },
  emits: ["enlarge-text"],
};
</script>


<template>
  <button
    @click="$emit(event)"
    class="mt-4 py-2 w-28 hover:w-32 text-white bg-slate-800 rounded hover:rounded-3xl transition-all"
  >
    {{ text }}
  </button>
</template>