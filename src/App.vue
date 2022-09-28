<template>
  <!-- RECOMMENDATION: Look at src/components/Penguin.vue, first to see visual feedback -->
  <div id="app">
    <div>
      <h2>List of Penguins</h2>
      <!-- These two buttons are linked to the methods found below -->
      <button @click="moveBestPenguinToTop">Move best penguin to top</button>
      <button @click="moveWorstPenguinToBottom">
        Move worst penguin to bottom
      </button>
      <!-- Visit Penguin.vue and make this data display -->
      <penguin
        v-for="penguin in penguins"
        :key="penguin.name"
        :penguin="penguin"
      />
    </div>

    <div>
      <h2>Best Penguin</h2>
      <penguin :penguin="bestPenguin" />
    </div>

    <div>
      <h2>Worst Penguin</h2>
      <penguin :penguin="worstPenguin" />
    </div>
  </div>
</template>

<script>
import Penguin from './components/Penguin.vue';
export default {
  name: 'App',
  components: {
    Penguin,
  },
  computed: {
    // NOTE: these computed values will be utilized by the Penguin.vue component ( see template )
    bestPenguin() {
      // find the penguin with the highest rating in the array and return it
      // access the penguin list using `this.penguins`
      const best = this.penguins.sort((a, b) => b.rating - a.rating);
      return best[0];
    },

    worstPenguin() {
      // find the penguin with the lowest rating in the array and return it
      const worst = this.penguins.sort((a, b) => a.rating - b.rating);
      return worst[0];
    },
  },

  methods: {
    moveBestPenguinToTop() {
      this.penguins.sort((a, b) => b.rating - a.rating);
    },

    moveWorstPenguinToBottom() {
      this.penguins.sort((a, b) => b.rating - a.rating);
    },
  },
  data() {
    return {
      penguins: [
        {
          name: 'Yellow Eyed',
          rating: 4,
        },
        {
          name: 'Humboldt',
          rating: 4,
        },
        {
          name: 'Emperor',
          rating: 1,
        },
        {
          name: 'King',
          rating: 5,
        },
        {
          name: 'Fiordland',
          rating: 2,
        },
        {
          name: 'Snares',
          rating: 3,
        },
      ],
    };
  },
};
</script>

<style></style>
