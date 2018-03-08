<template>
    <div class="container">
        <tutorial-step></tutorial-step>
    </div>
</template>

<script>
  import TutorialStep from './components/TutorialStep.vue'

  export default {
    name: 'app',
    components: {
      TutorialStep,
    },
    data() {
      return {
        msg: 'Welcome to Your Vue.js App',
      }
    },
  }
</script>

<style lang="scss">
    body {
        font-family:      'Avenir', Helvetica, Arial, sans-serif;
        color:            #2c3e50;
        background-color: #FAF9F5;
        margin-top:       60px;
    }

    h1, h2 {
        font-weight: normal;
    }

</style>
