<template>
  <div class="flex-container">
    <div v-for="item in bookdetails" :key="item.id" class="container">
      <h2> StudentName: {{ item.Customername }} <hr></h2>
      <p>Student Id:{{ item.customerid }}</p>
      <p>Book Name: {{ item.bookname }}</p>
      <p>Book Id: {{ item.bookid }}</p>
      <p>Borrowed Date: {{ item.borroweddate }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BookDetails',
  props: {
    bookdetails: Array,
  },
};
</script>

<style scoped>
.flex-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  margin: 10px;
}

.container {
  display: grid;
  grid-template-rows: repeat(5, 1fr);
  width: 90%;
  padding: 5px;
  background-color: #16d616;  
}
</style>