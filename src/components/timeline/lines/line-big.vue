<template>
  <div id="wrapper">
    <div class="line"></div>
    <a>{{ year }}</a>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

const props = defineProps({
  year: {
    type: Number,
    required: true,
  },
});
</script>

<style scoped lang="scss">
@import "@/styles/variables.scss";

.line {
  color: $sov-red;
  background-color: $sov-red;
  width: 4px;
  height: 35px;
  border-radius: 5px;
  border-width: 1px;
}

#wrapper {
	width: 40px;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
}
</style>
