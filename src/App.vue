<template>
  <div id="app">
    <div class="columns">
      <div class="column"></div>
      <div class="column">
        <div class="resume">
          <resume/>
        </div>
      </div>
      <div class="column"></div>
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
  background: #eee!important;
}
@font-face{
  font-family: Lato;
  src: url("assets/typo/Lato-Regular.ttf") format("truetype");
  font-weight: normal;
  font-style: normal;
}
@font-face{
  font-family: Lato;
  src: url("assets/typo/Lato-Bold.ttf") format("truetype");
  font-weight: bold;
  font-style: normal;
}

#app {
  font-family: Lato, Ubuntu, Helvetica, sans-serif;
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
