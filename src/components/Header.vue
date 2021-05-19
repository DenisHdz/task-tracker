<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      v-show="homePage"
      @button-click="$emit('toggle-add-task')"
      :text="displayForm ? 'Close' : 'Add'"
      :color="displayForm ? 'Red' : 'Green'"
    />
  </header>
</template>

<script>
import Button from "./Button";

export default {
  name: "Header",
  props: {
    title: String,
    displayForm: Boolean,
  },
  components: {
    Button,
  },
  computed: {
    homePage() {
      if (this.$route.path === "/") {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>

<style>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
