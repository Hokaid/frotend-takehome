<template>
  <ul>
    <li>
      <input type="radio">
      <label>HTML</label>
      <input placeholder="Rate from 1 to 5">
    </li>
    <li>
      <input type="radio">
      <label>Javascript</label>
      <input placeholder="Rate from 1 to 5">
    </li>
    <li>
      <input type="radio">
      <label>CSS</label>
      <input placeholder="Rate from 1 to 5">
    </li>
    <li>
      <input type="radio">
      <label>PHP</label>
      <input placeholder="Rate from 1 to 5">
    </li>
    <li>
      <input type="radio">
      <label>Ruby</label>
      <input placeholder="Rate from 1 to 5">
    </li>
    <li>
      <input type="radio">
      <label>TypeScript</label>
      <input placeholder="Rate from 1 to 5">
    </li>
    <li>
      <input type="radio">
      <label>Docker</label>
      <input placeholder="Rate from 1 to 5">
    </li>
    <li>
      <input type="radio">
      <label>React</label>
      <input placeholder="Rate from 1 to 5">
    </li>
    <li>
      <input type="radio">
      <label>Angular</label>
      <input placeholder="Rate from 1 to 5">
    </li>
    <li>
      <input type="radio">
      <label>Pythons</label>
      <input placeholder="Rate from 1 to 5">
    </li>
  </ul>
  <button @click="getJobs()">Buscar</button>
  <ul>
    <li v-for="item in jobs" :key="item.id">
      {{ item.title }}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'MainPage',
  jobs: [],
  data() {
    return {
      jobs: null,
    };
  },
  methods: {
    async getJobs() {
      let response = await fetch("https://private-anon-fade43cc98-jobscantakehomeprojectapi.apiary-mock.com/postings/search/skills?skill=");
      let data = await response.json();
      this.jobs = data.results;
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
