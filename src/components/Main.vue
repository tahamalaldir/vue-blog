<template
  ><div class="work">
    <b-row><h1 class="text">Work</h1></b-row>
    <b-row>
      <a
        v-for="user in users"
        :key="user.id"
        :href="user.html_url"
        target="blank"
      >
        <b-card-group v-if="!user.fork" class="group"
          ><b-card class="text-center">
            <b-card-title>{{ user.name }}</b-card-title>
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
    <b-row><h1 class="text">Fork</h1></b-row>
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
</template>

<script>
export default {
  data() {
    return {
      users: []
    }
  },
  name: 'Main',
  created() {
    fetch('https://api.github.com/users/tahamalaldir/repos')
      .then(response => response.json())
      .then(data => {
        this.users = data
      })
    console.log(this.users)
  }
}
</script>

<style>
.work {
  padding-right: 20px;
  padding-top: 100px;
}
.text {
  font-size: 4rem;
}
.group {
  float: left;
  color: #41444b;
}
.card {
  width: 450px;
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
  background-color: white;
}
.card:before {
  content: '';
  position: absolute;
  z-index: -1;
  top: -16px;
  right: -16px;
  background: #41444b;
  height: 32px;
  width: 32px;
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
