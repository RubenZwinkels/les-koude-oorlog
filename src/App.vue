<template>
  <h1>De Koude oorlog</h1>
  <h2>De berlijnse muur</h2>
  <p>De val van de berlijnse muur</p>
  <line-big :year="1989" />
  <line-current :year="1989" />
  <line-small />
</template>

<script setup>
import lineBig from "@/components/timeline/lines/line-big.vue";
import lineSmall from "@/components/timeline/lines/line-small.vue";
import lineCurrent from "@/components/timeline/lines/line-current.vue";
</script>

<style lang="scss">
@import "@/styles/variables.scss";
</style>
