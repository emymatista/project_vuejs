<!-- src/components/SimpleForm.vue -->
<template>
    <div>
      <h1>Simple Form</h1>
      <form @submit.prevent="handleSubmit">
        <div>
          <label for="name">Name:</label>
          <input type="text" id="name" v-model="formData.name" />
        </div>
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="formData.email" />
        </div>
        <button type="submit">Submit</button>
      </form>
      <div v-if="submitted">
        <h2>Submitted Data</h2>
        <p>Name: {{ formData.name }}</p>
        <p>Email: {{ formData.email }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        formData: {
          name: '',
          email: ''
        },
        submitted: false
      };
    },
    methods: {
      handleSubmit() {
        this.submitted = true;
        console.log('Form submitted:', this.formData);
        // Here, you can also make an API call to submit the form data
      }
    }
  };
  </script>
  
  <style scoped>
  /* Add some basic styling */
  div {
    margin-bottom: 10px;
  }
  
  label {
    display: inline-block;
    width: 70px;
  }
  
  input {
    padding: 5px;
    margin-bottom: 10px;
  }
  
  button {
    padding: 5px 10px;
  }
  </style>
  