<template>
  <!--
  <h1>De Koude oorlog</h1>
  <h2>De berlijnse muur</h2>
  <p>De val van de berlijnse muur</p>
  <line-big :year="1989" />
  <line-current :year="1989" />
  <line-small />
-->
  <time-line
    :startyear="startyear"
    :endyear="endyear"
    :highlightyears="highlightyears"
    :currentyear="currentyear"
		@eCurrentYear="currentyear = $event"
  />
</template>

<script setup>
import lineBig from "@/components/timeline/lines/line-big.vue";
import lineSmall from "@/components/timeline/lines/line-small.vue";
import lineCurrent from "@/components/timeline/lines/line-current.vue";
import timeLine from "@/components/timeline/time-line.vue";
import {ref} from "vue";

const startyear = 1945;
const endyear = 1989;
const highlightyears = [1945, 1963, 1989];
let currentyear = ref(1950);

</script>

<style lang="scss">
@import "@/styles/variables.scss";
</style>
