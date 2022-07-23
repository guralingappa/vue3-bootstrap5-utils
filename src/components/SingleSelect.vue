<template>
  <div class="container g-single-select">
    <div class="row">
      <label class="form-label col" for="singleselect" v-if="showLabel">{{
        label
      }}</label>
      <select
        id="singleselect"
        v-model="model"
        class="form-select col"
      >
        <option v-if="showDefaultText">{{ defaultText }}</option>
        <option
          v-for="option in options"
          :key="option.value"
          :value="option.value"
        >
          {{ option.text }} <img alt="text" width="10px" height="10px" />
        </option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: "SingleSelect",
  props: {
    modelValue: [String, Number],
    options: {
      type: Array,
      default: function () {
        return [];
      },
    },
    showLabel: {
      type: Boolean,
      default: false,
    },
    label: {
      type: String,
    },
    showDefaultText: {
      type: Boolean,
      default: false,
    },
    defaultText: {
      type: String,
    },
  },
  computed: {
    model: {
      get() {
        return this.modelValue;
      },
      set(value) {
        this.$emit("update:modelValue", value);
      },
    },
  },
};
</script>

<style type="css">
.g-single-select label.form-label {   
        margin:auto 0;
        text-align: right;  
}
</style>