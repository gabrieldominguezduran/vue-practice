<template>
  <Form/>
  <hr />
  <Quiz/>
</template>

<script>

import {defineComponent} from "vue";
import Form from "@/components/Form/Form.vue";
import Quiz from "@/components/Quiz/Quiz.vue";

export default defineComponent({
  components: {Form, Quiz}
});
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  font-size: 20px;
  font-family: sans-serif;
  padding-top: 20px;
  background: #e6ecf1;
}

hr {
  margin: 3rem 0;
}
</style>

