<template>
  <div id="app">
    <div class="resume">
      <resume/>
    </div>
  </div>
</template>

<script>
//import Resume from './components/Resume.bak.vue'
import resume from './components/resume'

export default {
  name: 'App',
  components: {
    resume
  }
}
</script>

<style>
html{
  background: #eee;
}
#app {
  font-family: Ubuntu, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.resume{
  height: 297mm;
  width: 210mm;
  margin: 10px;
}
</style>
