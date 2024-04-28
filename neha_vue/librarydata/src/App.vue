<template>
  <div id="app">
    <my-header :UniversityName="appTitle" :AuthorName="Name" />
    <book-details :bookdetails="studentdetails" />
    <my-footer :countbooks="numberofoverduebooks" />
    <div v-if="loading">Loading...</div>
    
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import BookDetails from './components/BookDetails.vue';
import MyFooter from './components/MyFooter.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    BookDetails,
    MyFooter,
  },
  data() {
    return {
      appTitle: 'University Of New Haven Library Management System',
      Name: 'Neha Vontari',
      studentdetails: [],
      numberofoverduebooks: new Date().getMonth(),
      loading: true,
      error: null,
    };
  },
  methods: {
    async fetchdetails() {
      try {
        const response = await fetch('https://node-librarydata.onrender.com/api');
        if (!response.ok) {
          throw new Error('Network response was not ok');
        }
        const data = await response.json();
        this.studentdetails = data;
        console.log('Data fetched:', data);
      } catch (error) {
        console.error('Error fetching news feed:', error.message);
        this.error = 'Error fetching data. Please try again later.';
      } finally {
        this.loading = false;
      }
    },
  },
  async created() {
    await this.fetchdetails();
  },
};
</script>

<style>
body {
  font-family: 'Montserrat', sans-serif;
  margin: 0;
  padding: 0;
}

#app {
  text-align: center;
  margin-top: 20px;
}

#app div {
  margin-top: 10px;
  font-weight: bold;
  color: black;
}

.loading {
  color: #00f;
}

.error {
  color: #f00;
}
</style>