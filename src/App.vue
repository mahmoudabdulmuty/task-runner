<template>
  <user-profile />
</template>

<script>
import userProfile from "./components/userProfile.vue";
export default {
  components: { userProfile },
  name: "App",
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
