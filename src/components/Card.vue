<template>
  <b-row>
    <a
      v-for="user in users"
      :key="user.id"
      :href="user.html_url"
      target="blank"
    >
      <b-card-group v-if="user.fork === isFork" class="group"
        ><b-card class="text-center">
          <b-card-title>{{ user.name }}</b-card-title>
          <b-card-text>{{ user.description }}</b-card-text>
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
    ></b-row
  >
</template>

<script>
export default {
  props: {
    users: Array,
    isFork: Boolean
  },
  name: 'Card'
}
</script>

<style>
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
  border-radius: 4px;
  padding: 32px 24px;
  margin: 12px;
  text-decoration: none;
  z-index: 0;
  overflow: hidden;
}
.card:hover {
  -webkit-transition: all 0.2s ease-out;
  transition: all 0.2s ease-out;
  box-shadow: 0px 4px 8px rgba(38, 38, 38, 0.2);
  top: -4px;
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
