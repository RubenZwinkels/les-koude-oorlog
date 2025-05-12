<template>
  <div id="wrapper">
    <div class="line"></div>
    <h2>{{ year }}</h2>
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
  width: 7px;
  height: 44px;
  border-radius: 5px;
  border-width: 1px;
	margin: 0px;
}

#wrapper {
	width: 60px;
	height: 150px;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
}
h2 {
	background-color: $sov-red;
	color: white;
	height: 30px;
	width: 70px;
	margin: -2px;
}
</style>
