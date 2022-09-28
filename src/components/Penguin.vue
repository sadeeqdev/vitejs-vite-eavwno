<template>
  <li>
    <!-- Display the penguin's name and rating. -->
    <!-- The penguin is being passed as a prop -->
    {{penguin.name}} - {{penguin.rating}}
  </li>
</template>

<script>
export default {
  props: {
    penguin: {
      type: Object,
      default: () => ({}),
    },
  },
};
</script>
