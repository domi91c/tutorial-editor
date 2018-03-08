<template>
    <div>
        <h4>Step 1</h4>
        <b-card>
            <b-form-group id="stepTitleGroup">
                <b-form-input id="stepTitleInput"
                              type="text"
                              required
                              placeholder="Step title...">
                </b-form-input>
            </b-form-group>
            <b-form-group>
                <trix-vue placeholder="Step instructions..."></trix-vue>
            </b-form-group>
            <div class="row">
                <step-image-input>
                </step-image-input>
                <step-image
                        @preview-image="cropImage"
                        :image="sampleImages[0]">
                </step-image>
                <step-image
                        @preview-image="cropImage"
                        :image="sampleImages[1]">
                </step-image>
                <step-image
                        @preview-image="cropImage"
                        :image="sampleImages[2]">
                </step-image>
            </div>
        </b-card>
        <crop-modal :image="selectedImage"></crop-modal>
    </div>
</template>

<script>
  import TrixVue from './TrixVue.vue'
  import StepImage from './StepImage.vue'
  import CropModal from './CropModal.vue'
  import StepImageInput from './StepImageInput.vue'

  import animalImage from '../assets/images/animals.jpg'
  import techImage from '../assets/images/tech.jpg'
  import archImage from '../assets/images/arch.jpg'

  export default {
    components: {
      TrixVue,
      StepImage,
      CropModal,
      StepImageInput,
    },
    mounted() {

    },

    data() {
      return {
        selectedImage: '',
        sampleImages: [animalImage, techImage, archImage],
      }
    },

    methods: {
      cropImage(image) {
        this.selectedImage = image
        this.$root.$emit('bv::show::modal', 'cropModal')
      },
    },
  }
</script>

<style lang="scss" rel="stylesheet/scss" scoped>
    /*@import "./resources/assets/sass/variables";*/


</style>