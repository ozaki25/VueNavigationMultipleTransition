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

const original = AppNavigation.router.getStateForAction;

AppNavigation.router.getStateForAction = (action, state) => {
  if (state && action.routeName === state.routes[state.index].routeName) {
    console.log("二重遷移抑止", { state, action });
    return null;
  }
  console.log("二重遷移じゃないのでOK", { state, action });
  return original(action, state);
};

export default {
  components: { AppNavigation }
};
</script>