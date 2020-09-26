<template>
  <div class="work">
    <h1 class="text">Work</h1>
    <a
      v-for="user in users"
      :key="user.id"
      :href="user.html_url"
      target="blank"
    >
      <b-card-group class="group"
        ><b-card class="text-center">
          <b-card-title>{{ user.name }}</b-card-title>
          <b-card-footer>
            <span v-if="user.language"><i class="fas fa-code"></i>&nbsp; </span>
            {{ user.language }}
            <span><i class="fas fa-star"></i>&nbsp; </span
            >{{ user.stargazers_count }}
            <span><i class="fas fa-code-branch"></i>&nbsp; </span
            >{{ user.forks_count }}
          </b-card-footer>
        </b-card></b-card-group
      ></a
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
  font-size: 5rem;
}
.group {
  margin-bottom: 20px;
  margin-right: 20px;
  width: 450px;
  float: left;
}
.card {
  display: block;
  position: relative;
  max-width: 450px;
  background-color: #41444b;
  border-radius: 4px;
  padding: 32px 24px;
  margin: 12px;
  text-decoration: none;
  z-index: 0;
  overflow: hidden;
  float: left;
  color: #41444b;
}
.card:before {
  content: '';
  position: absolute;
  z-index: -1;
  top: -25px;
  right: -25px;
  background: #41444b;
  height: 50px;
  width: 50px;
  border-radius: 32px;
  -webkit-transform: scale(1);
  transform: scale(1);
  -webkit-transform-origin: 50% 50%;
  transform-origin: 50% 50%;
  -webkit-transition: -webkit-transform 0.25s ease-out;
  transition: -webkit-transform 0.25s ease-out;
  transition: transform 0.25s ease-out;
  transition: transform 0.25s ease-out, -webkit-transform 0.25s ease-out;
  color: #ffffff;
}
.card:hover:before {
  -webkit-transform: scale(21);
  transform: scale(21);
  color: rgba(255, 255, 255, 0.8);
}

.card:hover {
  -webkit-transition: all 0.3s ease-out;
  transition: all 0.3s ease-out;
  color: rgba(255, 255, 255, 0.8);
}
.card:hover b-card-title {
  -webkit-transition: all 0.3s ease-out;
  transition: all 0.3s ease-out;
  color: #ffffff;
}
.deneme:hover {
  -webkit-transition: all 0.3s ease-out;
  transition: all 0.3s ease-out;
  color: #ffffff;
}
</style>
