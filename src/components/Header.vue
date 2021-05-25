<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      v-show="homePage"
      :text="showAddTask ? 'Close' : 'Add task'"
      :color="showAddTask ? 'red' : 'green'"
      @btn-click="$emit('toggle-form')"
    />
  </header>
</template>

<script>
import Button from "./Button.vue";

export default {
  name: "Header",
  props: {
    title: String,
    showAddTask: Boolean,
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
  components: { Button },
};
</script>



<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>