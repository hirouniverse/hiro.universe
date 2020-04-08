<template>
  <div>
    <input v-model="msg" />
    <p>prop: {{ propMessage }}</p>
    <p>msg: {{ msg }}</p>
    <p>helloMsg: {{ helloMsg }}</p>
    <p>computedMsg: {{ computedMsg }}</p>
    <button @click="greet">Greet</button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Component from "vue-class-component";

@Component
export default class WithDecorator extends Vue {
  msg = "Hiro";
  helloMsg = "Hello, " + this.msg;

  mounted() {
    this.greet();
  }

  get computedMsg() {
    return "computed " + this.msg;
  }

  greet() {
    alert("greeting " + this.msg);
  }
}
</script>
