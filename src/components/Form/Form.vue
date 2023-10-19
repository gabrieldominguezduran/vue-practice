<!--suppress HtmlUnknownTarget -->
<template>
  <div id="wrapper">
    <form @submit.prevent="submit">
      <FormInput
        name="Username"
        :rules="{ required: true, min: 5 }"
        :value="username.value"
        type="text"
        @update="update"
      />

      <FormInput
        name="Password"
        :rules="{ required: true, min: 10 }"
        :value="password.value"
        type="password"
        @update="update"
      />

      <FormButton
        color="white"
        background="darkslateblue"
        :disabled="!valid"
      />
    </form>
  </div>
</template>

<script>
import FormButton from "@/components/Form/FormButton.vue";
import FormInput from "@/components/Form/FormInput.vue";

export default {
  components: {
    FormButton,
    FormInput
  },

  data() {
    return {
      username: {
        value: '',
        valid: false
      },
      password: {
        value: '',
        valid: false
      }
    }
  },

  computed: {
    valid() {
      return this.username.valid && this.password.valid
    }
  },

  methods: {
    submit() {
      console.log('Submit')
    },

    update(payload) {
      this[payload.name] = {
        value: payload.value,
        valid: payload.valid
      }
    }
  }
}

</script>

<style scoped>
#wrapper {
  display: flex;
  justify-content: center;
  margin-top: 2rem;
}

body {
  font-family: Arial, sans-serif;
}

form {
  max-width: 400px;
  width: 50%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

</style>
