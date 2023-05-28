<script>
import BaseInput from "@/components/BaseInput.vue";

export default {
  name: "TestView",
  components: { BaseInput },
  data: () => ({
    title: "Test",
    input: {
      name: "",
      email: "",
      selected: "",
    },
  }),
  methods: {
    handleSubmit() {
      console.log(this.input);
    },
  },
};
</script>

<template>
  <div class="test">
    <h1>{{ title }}</h1>
    <form @submit.prevent="handleSubmit">
      <BaseInput v-model="input.name" name="name" label="Name" type="text" />
      <BaseInput
        v-model="input.email"
        name="email"
        label="Email"
        type="email"
      />
      <br />
      <select v-model="input.selected">
        <option value="A">A</option>
        <option value="B">B</option>
        <option value="C">C</option>
      </select>
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .test {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
}
</style>
