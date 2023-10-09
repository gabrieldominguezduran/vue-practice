<!--suppress HtmlUnknownTarget -->
<template >
  <main class="container">
    <FormInput name="Username"/>
    <FormButton
      background="darkslateblue"
      color="white"
      :disabled="!valid"
    />
  </main>
</template>

<script>
import FormButton from "@/components/Form/FormButton.vue";
import FormInput from "@/components/Form/FormInput.vue";

export default {
  components: {FormInput, FormButton},
  data() {
    return {
      valid: true
    }

  }

}

</script>

<style scoped>

.container {
  position: absolute;
  top: 20%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>
