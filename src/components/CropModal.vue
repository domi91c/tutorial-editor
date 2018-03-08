<template>
    <div>
        <b-modal id="cropModal" title="Crop"
                 no-close-on-backdrop
                 hide-header-close>
            <img v-show="false" :src="image" alt="">
            <vue-cropper
                    ref='cropper'
                    :aspect-ratio="10/9"
                    :guides="false"
                    :view-mode="1"
                    :drag-mode="'move'"
                    :min-container-height="400"
                    :auto-crop-area="0.5"
                    :background="false"
                    :rotatable="true">
            </vue-cropper>
        </b-modal>
    </div>
</template>

<script>
  //import { mapState, mapActions, mapMutations } from 'vuex';
  import VueCropper from 'vue-cropperjs'

  export default {
    components: {
      VueCropper,
    },
    props: ['image'],
    data() {
      return {}
    },
    updated() {
      if (this.image) {
        console.log('url found in update')
        this.$refs.cropper.replace(this.image)
      }
    },
    mounted() {
      console.log(this.image)
      alert(this.image)
      this.$refs.cropper.replace(this.image)
    },
    methods: {},
  }
</script>

<style lang="scss" rel="stylesheet/scss" scoped>
    /*@import "./resources/assets/sass/variables";*/


</style>