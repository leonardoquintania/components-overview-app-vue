<template>
  <h1>Local component</h1>
  <h2>{{ title }}</h2>
  <!-- <button @click="$emit('addClick')">Add</button> -->
  <button @click="$emit('addClick', 1)">Add</button>
  <button @click="$emit('addClick', 2)">Add Two</button>
  <br />
  <slot name="header" />
  <br />
  <slot name="content" />
</template>

<script>
export default {
  //props: ['title'],
  props: {
    title: String, //-- Number, Object Boolean Array Function
  },
  data() {},
  methods: {
    add: function() {
      this.$emit('addClick', 2);
    },
  },
};
</script>

<style scoped></style>
