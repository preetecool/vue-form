<template>
  <ul>
    <li :class="{ active: modelValue === 'poor' }">
      <button type="button" @click="selectButton('poor')">Poor</button>
    </li>
    <li :class="{ active: modelValue === 'average' }">
      <button type="button" @click="selectButton('average')">Average</button>
    </li>
    <li :class="{ active: modelValue === 'great' }">
      <button type="button" @click="selectButton('great')">Great</button>
    </li>
  </ul>
</template>

<script>
export default {
  props: ['modelValue'],
  emits: ['update:modelValue'],
  //   data() {
  //     return {
  //       activeOption: null,
  //     };
  //   },
  computed: {
    activeOption() {
      return this.modelValue;
    },
  },
  methods: {
    selectButton(selection) {
      this.$emit('update:modelValue', selection);
    },
  },
};
</script>

<style scoped>
.active {
  border-color: blue;
}

.active button {
  color: blue;
}

li:hover {
  background-color: rgba(0, 0, 255, 0.171);
}

ul {
  list-style: none;
  margin: 0.5rem 0;
  padding: 0;
  display: flex;
}

li {
  margin: 0 1rem;
  border: 1px solid #ccc;
  padding: 1rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

button {
  font: inherit;
  border: none;
  background-color: transparent;
  cursor: pointer;
}
</style>
