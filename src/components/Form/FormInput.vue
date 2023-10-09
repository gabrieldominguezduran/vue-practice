<template>
 <div class="label">
   <label :for="name"> {{ name }}</label>
 </div>
  <input :id="name" />
</template>

<script>
export default {
props: {
  name: {
    type: String,
    required: true
  }
}

}

</script>

<style scoped>
.input-wrapper {
  display: flex;
  justify-content: center;
}
.error {
  color: red;
}
.label {
  display: flex;
  justify-content: space-between;
}
input {
  background: none;
  color: black;
  border: 1px solid silver;
  padding: 10px;
  margin: 5px 0;
  font-size: 16px;
}
</style>
