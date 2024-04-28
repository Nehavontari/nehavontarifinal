<template>
    <div class="header">
      <h1>{{ UniversityName }}</h1>
      <h1> Librarian :{{ AuthorName }}</h1>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      UniversityName: {
        type: String,
        required: true,
      },
      AuthorName: {
        type: String,
        required: true,
      },
    },
  };
  </script>
  
  <style scoped>
  .header {
    background-color: #4c56af;
    text-align: center;
    padding: 1em;
  }
  .header h1{
    color: white;
  }
  </style>
  
  
