<template>
  <div class="work">
    <div v-if="isLoading">
      <h1 class="text">Loading...</h1>
    </div>
    <div v-else>
      <b-row><h1 class="text">Works</h1></b-row>
      <Card :isFork="false" :users="users" />
      <b-row><h1 class="text">Forks</h1></b-row>
      <Card :isFork="true" :users="users" />
    </div>
  </div>
</template>

<script>
import Card from './Card.vue'
export default {
  components: { Card },
  data() {
    return {
      users: [],
      isLoading: true
    }
  },
  name: 'Main',
  created() {
    fetch('https://api.github.com/users/tahamalaldir/repos')
      .then(response => response.json())
      .then(data => {
        this.users = data
        this.isLoading = false
      })
  }
}
</script>

<style scoped>
.work {
  padding: 100px 10px 200px 10px;
}
.text {
  font-size: 4rem;
  padding-left: 10px;
  padding-top: 10px;
  font-weight: bold;
}
</style>
