<template>
  <app-navigation></app-navigation>
</template>

<script>
import { StackNavigator } from "vue-native-router";
import Sample1 from "./src/screens/Sample1.vue";
import Sample2 from "./src/screens/Sample2.vue";
const AppNavigation = StackNavigator(
  {
    Sample1: Sample1,
    Sample2: Sample2
  },
  {
    initialRouteName: "Sample1"
  }
);
export default {
  components: { AppNavigation }
};
</script>