<template>
  <div id="wrapper">
    <div id="base"></div>
		<div id="line-wrapper">
    <div id="lines" v-for="year in years" :key="year">
			<line-small />
		</div>
		</div>
  </div>
</template>

<script setup>
import lineBig from "@/components/timeline/lines/line-big.vue";
import lineSmall from "@/components/timeline/lines/line-small.vue";
import lineCurrent from "@/components/timeline/lines/line-current.vue";
import {defineProps} from 'vue';

const props = defineProps({
  startyear: {
    type: Number,
    required: true,
  },
  endyear: {
    type: Number,
    required: true,
  },
});

const years = Array.from({ length: props.endyear - props.startyear + 1 }, (_, i) => props.startyear + i);
</script>

<style scoped lang="scss">
@import "@/styles/variables.scss";

#wrapper {
  width: 95%;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

#base {
  background-color: $usa-blue;
  color: $usa-blue;
  width: 100%;
  height: 19px;
  border-radius: 16px;
}
#line-wrapper {
	width: 100%;
	margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: center;
}
</style>
