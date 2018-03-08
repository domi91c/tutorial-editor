<template>
    <div class="d-inline col-4 col-sm-3">
        <div class="step-image-button img-fluid  img-thumbnail">
            <div class="">
                <i class=" fa fa-2x fa-camera">
                    <p>Add image.</p>
                </i>
            </div>
        </div>
    </div>
</template>
<script>

  export default {
    props: ['step', 'image'],
    methods: {
      deleteImage() {
        this.$store.dispatch('DELETE_IMAGE',
            { step: this.step, image: this.image })
      },
    },
  }
</script>


<style lang="scss" rel="stylesheet/scss" scoped>
    /*@import "./resources/assets/sass/variables";*/

    .step-image-button {
        position:       relative;
        padding-bottom: 85%;
        margin-top:     15px;

        i {
            top:       50%;
            position:  absolute;
            left:      50%;
            transform: translate(-50%, -50%);
            text-align: center;

            p {
                margin-top:  10px;
                font-family: Avenir, serif;
                font-size:   12px;
            }
        }

    }
</style>
