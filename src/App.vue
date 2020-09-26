<template>
  <div id="app" class="text-monospace">
    <b-row>
      <b-col cols="4"><Nav /></b-col>
      <b-col><Main /></b-col>
    </b-row>
  </div>
</template>

<script>
import Main from './components/Main.vue'
import Nav from './components/Nav.vue'
export default {
  components: { Main, Nav }
}
</script>

<style></style>
