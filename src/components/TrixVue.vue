<template>
    <div class="trixWrapper">
        <div ref="trixContainer" :id="id">
            <trix-editor :input="inputId" :placeholder="placeholder"></trix-editor>
        </div>
    </div>
</template>

<script>
  import 'trix'
  import 'trix/dist/trix.css'

  export default {
    name: 'trix-vue',

    props: {
      id: {
        type: String,
        default: 'trix-container',
      },
      inputId: {
        type: String,
        default: '',
      },
      placeholder: {
        type: String,
        defaults: '',
      },
    },

    data() {
      return {}
    },

    methods: {},
  }
</script>

<style>
    #trix-container {
    }
</style>
