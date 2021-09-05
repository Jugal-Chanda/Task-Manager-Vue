<template>
  <!-- <button class="btn" :style="{ background: color }" v-on:click="onClick()">
    {{ text }}
  </button> -->
  <button class="btn" :style="{ background: color }" @click="onClick()">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
  },
  methods: {
    onClick() {
      // console.log("Hello");
      this.$emit("btn-click");
    },
  },
};
</script>
