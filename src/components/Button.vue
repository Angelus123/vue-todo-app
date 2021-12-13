<template>
  <button
    @click="onClick()"
    :style="{
      background: color,
    }"
  >
    {{ title }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    title: String,
  },
  methods: {
      onClick () {
          console.log('click');
      }
  }
};
</script>
