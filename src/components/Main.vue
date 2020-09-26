<template>
  <div class="work">
    <div v-if="isLoading">
      <h1 class="text">Loading...</h1>
    </div>
    <div v-else>
      <b-row><h1 class="text">Works</h1></b-row>
      <b-row class="row">
        <a
          v-for="user in users"
          :key="user.id"
          :href="user.html_url"
          target="blank"
        >
          <b-card-group v-if="!user.fork" class="group"
            ><b-card class="text-center">
              <b-card-title>{{ user.name }}</b-card-title>
              <b-card-text>{{ user.description }}</b-card-text>
              <b-card-footer>
                <span v-if="user.language"
                  ><i class="fas fa-code"></i>&nbsp;
                </span>
                {{ user.language }}
                <span><i class="fas fa-star"></i>&nbsp; </span
                >{{ user.stargazers_count }}
                <span><i class="fas fa-code-branch"></i>&nbsp; </span
                >{{ user.forks_count }}
              </b-card-footer>
            </b-card></b-card-group
          ></a
        ></b-row
      >
      <b-row><h1 class="text">Forks</h1></b-row>
      <b-row>
        <a
          v-for="user in users"
          :key="user.id"
          :href="user.html_url"
          target="blank"
        >
          <b-card-group v-if="user.fork" class="group"
            ><b-card class="text-center">
              <b-card-title>{{ user.name }}</b-card-title>
              <b-card-text>{{ user.description }}</b-card-text>

              <b-card-footer>
                <span v-if="user.language"
                  ><i class="fas fa-code"></i>&nbsp;
                </span>
                {{ user.language }}
                <span><i class="fas fa-star"></i>&nbsp; </span
                >{{ user.stargazers_count }}
                <span><i class="fas fa-code-branch"></i>&nbsp; </span
                >{{ user.forks_count }}
              </b-card-footer>
            </b-card></b-card-group
          ></a
        ></b-row
      >
    </div>
  </div>
</template>

<script>
export default {
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

<style>
.work {
  padding: 100px 10px 200px 10px;
}
.text {
  font-size: 4rem;
  padding-left: 10px;
  padding-top: 10px;
  font-weight: bold;
}
.group {
  color: #41444b;
  float: left;
}
.card {
  width: 29.3rem;
  height: auto;
  display: block;
  top: 0px;
  position: relative;
  background-color: #f2f8f9;
  border-radius: 4px;
  padding: 32px 24px;
  margin: 12px;
  text-decoration: none;
  z-index: 0;
  overflow: hidden;
  border: 1px solid #f2f8f9;
}
.card:hover {
  -webkit-transition: all 0.2s ease-out;
  transition: all 0.2s ease-out;
  box-shadow: 0px 4px 8px rgba(38, 38, 38, 0.2);
  top: -4px;
  border: 1px solid #cccccc;
  background-color: #41444b;
  color: #f2f8f9;
}
.card:before {
  content: '';
  position: absolute;
  z-index: -1;
  top: -20px;
  right: -20px;
  background: white;
  height: 35px;
  width: 35px;
  border-radius: 32px;
  -webkit-transform: scale(2);
  transform: scale(2);
  -webkit-transform-origin: 50% 50%;
  transform-origin: 50% 50%;
  -webkit-transition: -webkit-transform 0.15s ease-out;
  transition: -webkit-transform 0.15s ease-out;
  transition: transform 0.15s ease-out;
  transition: transform 0.15s ease-out, -webkit-transform 0.15s ease-out;
}
.card:hover:before {
  -webkit-transform: scale(2.15);
  transform: scale(2.15);
}
</style>
