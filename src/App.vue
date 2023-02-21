<script>
import CounterButton from "./components/CounterButton.vue";
import EventButton from "./components/EventButton.vue";
import NavBar from "./components/NavBar.vue";
import Heading from "./components/Heading.vue";

export default {
  components: {
    CounterButton,
    EventButton,
    NavBar,
  },
  data() {
    return {
      counterButtons: [
        { id: 1, name: "One" },
        { id: 2 },
        { id: 3, name: "them" },
      ],
      eventButtons: [{ id: 1, text: "Enlarge Text", event: "enlarge-text" }],
      textSize: 0.75,
    };
  },
  methods: {
    enlargeText() {
      this.textSize >= 1.1 ? (this.textSize = 0.75) : (this.textSize += 0.05);
    },
  },
};
</script>

<template>
  <main
    :style="{ fontSize: textSize + 'em' }"
    class="flex flex-col items-center justify-between h-screen py-5 px-6 bg-gradient-to-b from-gray-200 to-gray-400"
  >
    <NavBar></NavBar>

    <body class="flex flex-col items-center justify-center">
      
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

    </body>

    <div></div>
  
  </main>
</template>