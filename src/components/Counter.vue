<template>
    <div>
        <h3 :class="className">Counter : {{ counter }}</h3>
        <h3>Class {{className}}</h3>
        <button @click="updateCounter()">Update</button>
        <button @click="undoCounter()">Undo</button>

    </div>
</template>

<script>
export default {
  data() {
    return {
      counter: 1
    };
  },
  computed: {
    className() {
      return this.counter % 2 ? "odd" : "event";
    }
  },

  methods: {
    updateCounter() {
      this.counter += 1;
    },
    undoCounter() {
      this.counter -= 1;
    }
  }
};
</script>

<style scoped>
div {
  color: red;
}
.odd {
  color: blue;
}
.even {
  color: chocolate;
}
</style>
