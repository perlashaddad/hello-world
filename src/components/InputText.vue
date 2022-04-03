<template>
  <div>
    <b-field
      :type="inputChanged ? 'is-success' : 'is-danger'"
      message="What do you want to search?"
    >
      <b-input
        size="is-small"
        v-model="textValue"
        placeholder="Write something"
        type="text"
      >
      </b-input>
      <p class="control">
        <b-button
          size="is-small"
          @click="onInput"
          type="is-primary"
          label="Change"
        />
      </p>
    </b-field>
    <Transition name="bounce">
      <p v-if="inputChanged">{{ textValue }}</p>
    </Transition>
  </div>
</template>

<script>
export default {
  name: "InputText",
  props: ["inputTitle"],
  data() {
    return {
      textValue: "",
      inputChanged: false,
    };
  },
  methods: {
    onInput() {
      this.inputChanged = true;
      this.$emit("update:inputUpdated", this.textValue);
    },
  },
};
</script>

<style lang="scss">
.bounce-enter-active {
  animation: bounce-in 0.5s;
}
.bounce-leave-active {
  animation: bounce-in 0.5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.25);
  }
  100% {
    transform: scale(1);
  }
}
</style>
