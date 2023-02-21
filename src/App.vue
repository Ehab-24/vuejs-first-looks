<script>
import CounterButton from "./components/CounterButton.vue";
import EventButton from "./components/EventButton.vue";

export default {
  components: {
    CounterButton,
    EventButton,
  },
  data() {
    return {
      counterButtons: [
        { id: 1, name: "One" },
        { id: 2 },
        { id: 3, name: "them" },
      ],
      eventButtons: [
        { id: 1, text: "Enlarge Text", event: "enlarge-text" }
      ],
      textSize: 0.75,
    };
  },
  methods: {
    enlargeText() {
      this.textSize >= 1.1
      ? this.textSize = 0.75
      : this.textSize += 0.05;
    },
  },
};
</script>

<template>
  <div
    :style="{ fontSize: textSize + 'em' }"
    class="
      flex flex-col
      items-center
      justify-center
      bg-gradient-to-b
      from-gray-200
      to-gray-400
      h-screen
    "
  >
    <h1 class="mb-4 text-orange-700 font-bold text-3xl">ThreeFace</h1>
    <CounterButton
      v-for="button in counterButtons"
      :key="button.id"
      :name="button.name"
    ></CounterButton>

    <EventButton
      v-for="button in eventButtons"
      :key="button.id"
      :text="button.text"
      :event="button.event"
      v-on:enlarge-text="() => enlargeText()"
    ></EventButton>
  </div>
</template>