<template>
  <h1>{{ getTitle }} {{ count }}</h1>
  <div class="container">
    <button @click="restar">restart</button>
    <button @click="reset">reset</button>
    <button @click="aumetar">Aumentar</button>
  </div>
</template> 

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Counter",
  props: {
    title: String,
    number: {
      type: Number,
      default: 10,
    },
  },
  data() {
    return {
      count: 0,
    };
  },
  methods: {
    restar() {
      return this.count--;
    },
    reset() {
      return (this.count = 0);
    },
    aumetar() {
      return this.count++;
    },
  },
  computed: {
    getTitle() {
      return this.title ? this.title : "Counter";
    },
  },
});
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
}

.container button {
  background-color: rgb(4, 160, 108);
  padding: 10px 22px;
  border: 1px solid transparent;
  border-radius: 1rem;
  color: #fff;
  font-size: 1rem;
}
</style>