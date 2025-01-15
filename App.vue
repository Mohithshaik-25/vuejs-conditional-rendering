<template>
  <div>
    <h1>{{ count }}</h1>
    <button @click="incr">Click</button>
    <button @click="dec">Decrement</button>
    <!-- Conditionally render ChildComponent -->
    <ChildComponent v-if="showChild" />
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue'; // Import the child component

export default {
  name: "App",
  components: {
    ChildComponent, // Register the child component
  },
  data() {
    return {
      count: 0, // Reactive variable
      showChild: false, // To control child component visibility
    };
  },
  methods: {
    incr() {
      this.count += 1; // Increment count
      this.showChild = false; // Hide child component when incremented
    },
    dec() {
      if (this.count > 0) {
        this.count -= 1; // Decrement count if greater than 0
      } else {
        this.showChild = true; // Show child component if count is 0
      }
    },
  },
};
</script>
