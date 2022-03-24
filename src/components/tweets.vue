<template>
  <span> {{ username }} {{ content }} </span>
</template>

<script>
export default {
  name: "tweets",
  props: {
    content: String,
    username: String,
  },
};
</script>

<style>
</style>