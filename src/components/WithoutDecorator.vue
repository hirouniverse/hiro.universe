<template>
  <div>
    <div class="greeting">Hello, {{ name }} {{ exclamationMarks }}</div>
    <button @click="decrement">-</button>
    <button @click="increment">+</button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  props: {
    name: {
      type: String,
      default: ""
    },
    initialEnthusiasm: {
      type: Number,
      default: 0
    }
  },
  data() {
    return {
      enthusiasm: this.initialEnthusiasm
    };
  },
  methods: {
    increment() {
      this.enthusiasm++;
    },
    decrement() {
      if (this.enthusiasm > 1) {
        this.enthusiasm--;
      }
    }
  },
  computed: {
    exclamationMarks(): string {
      return Array(this.enthusiasm + 1).join("!");
    }
  }
});
</script>
