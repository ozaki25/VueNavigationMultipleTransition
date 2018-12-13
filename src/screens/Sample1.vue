 <template>
  <touchable-opacity :on-press="onPress" class="container">
    <text class="text-color-primary">Sample1</text>
  </touchable-opacity>
</template>

<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-color-primary {
  color: blue;
}
</style>

<script>
export default {
  props: {
    navigation: {
      type: Object
    }
  },
  methods: {
    onPress: function() {
      this.navigation.navigate("Sample2");
    }
  }
};
</script>