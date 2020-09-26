<template>
  <div id="profile">
    <div
      id="profile_img"
      style="background: url(https://avatars0.githubusercontent.com/u/57813348?s=460&u=61e3a696c77a8128dfb4c5b5b1c22ed5b91a48f0&v=4) center;"
    ></div>
    <div id="username">
      <span style="display:block;">Taha Tevfikhan MALALDIR</span
      ><a href="https://github.com/tahamalaldir" target="blank"
        >@tahamalaldir</a
      >
    </div>
    <div id="userbio" style="display: block;">
      Düzce University Computer Engineering
    </div>
    <div id="about">
      <span style="display:block;"
        ><i class="fas fa-map-marker-alt"></i> &nbsp;&nbsp; İstanbul</span
      >
      <div class="socials">
        <span style="display:block;"
          ><a
            href="https://www.twitter.com/tahamalaldir"
            target="_blank"
            class="socials"
            ><i class="fab fa-twitter fa-2x"></i></a
        ></span>
        <span style="display:block;"
          ><a
            href="https://www.linkedin.com/in/tahamalaldir/"
            target="_blank"
            class="socials"
            ><i class="fab fa-linkedin-in fa-2x"></i></a
        ></span>
        <span style="display:block;"
          ><a
            href="https://github.com/tahamalaldir"
            target="_blank"
            class="socials"
            ><i class="fab fa-github fa-2x"></i></a
        ></span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Nav'
}
</script>

<style>
#profile {
  width: 30vw;
  padding: 4vh 3vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: left;
  background-color: #41444b;
  background-size: cover !important;
  background-repeat: no-repeat;
  position: fixed;
  color: #fff !important;
}
#profile_img {
  width: 180px;
  height: 180px;
  min-width: 180px;
  min-height: 180px;
  max-width: 180px;
  max-height: 180px;
  border-radius: 5px;
  background-size: cover !important;
  background-repeat: no-repeat !important;
}
#profile div {
  font-weight: bold;
  margin: 1.5vh 0px;
}
#about span {
  margin: 1vh 0px;
  display: block;
}
.socials {
  color: #fff;
  text-decoration: none;
  margin: 3vh 0px !important;
}
.socials span {
  display: inline-block !important;
  margin-right: 2vw !important;
  font-weight: normal !important;
}
.socials span a {
  font-weight: normal !important;
}
#username {
  font-size: 18px;
  font-weight: bold;
}
#username span {
  font-size: 24px;
}
#userbio {
  font-size: 26px;
  font-family: 'Questrial', sans-serif;
  width: 100%;
}
#about {
  font-size: 18px;
  font-family: 'Questrial', sans-serif;
}
#about a,
#username a {
  color: #fff !important;
  text-decoration: none;
  font-weight: bold;
}
</style>
