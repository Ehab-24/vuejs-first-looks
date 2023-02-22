<script>
export default {
  data() {
    return {
      count: 0,
    };
  },
  props: {
    name: {
      type: String,
      default: "me",
    },
  },
  methods: {
    increment() {
      this.count == 9 ? (this.count = 0) : this.count++;
    },
  },
};
</script>

<template>
  <button
    @click="increment()"
    class="w-56 hover:w-60 my-2 py-2 flex flex-col items-center justify-center border-2 text-black border-orange-700 font-semibold rounded hover:rounded-3xl transition-all"
  >
    <p>You clicked {{ name }} {{ count }} times.</p>
    <slot />
  </button>
</template>