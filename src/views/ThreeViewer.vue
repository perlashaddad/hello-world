<template>
  <div class="is-flex is-justify-content-space-evenly">
    <inputText
      v-for="index in arraySize"
      :key="index"
      :input-title="title + ' ' + index.toString()"
      :inputUpdated.sync="inputValue"
    />
  </div>
</template>

<script>
import InputText from "@/components/InputText.vue";
export default {
  name: "ThreeViewer",
  components: {
    InputText,
  },
  data() {
    return {
      inputText: "",
      title: "Hello WOrllldddd",
      arraySize: 5,
      inputValue: "",
    };
  },
  methods: {},
};
</script>

<style lang="scss"></style>
