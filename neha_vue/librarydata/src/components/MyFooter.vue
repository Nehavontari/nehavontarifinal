
<template>
  <footer>
    <h1> Number of Upcoming Book Returns/Submissions: {{ countbooks }} </h1>
  </footer>
</template>

<script>
export default {
  props: {
    countbooks: {
      type: Number,
      required: true,
    },
  },
};
</script>

<style scoped>

footer {
  background-color: #4c56af;
  padding: 10px;
  text-align: center;
}
</style>


