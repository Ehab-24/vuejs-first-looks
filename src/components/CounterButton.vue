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
    class="
      h-10
      w-52
      my-2
      hover:w-56
      border-2
      text-black
      border-purple-700
      font-semibold
      py-2
      rounded
      hover:rounded-3xl
      transition-all
    "
  >
    You clicked {{ name }} {{ count }} times.
  </button>
</template>