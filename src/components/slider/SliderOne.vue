<template>
  <!-- Start Slider Area  -->
  <div class="rn-slider-area">
    <!-- Start Single Slide  -->
    <div
      class="slide slide-style-1 slider-fixed--height d-flex align-center bg_image bg_image--1"
      data-black-overlay="6"
    >
      <v-container class="position-relative">
        <v-row>
          <v-col cols="3">
            <div class="inner">
            <img src="../../assets/images/logo/rooster.svg" width="100%" class="theRooster" alt="">
            </div>
          </v-col>
          <v-col cols="9">
            <div class="inner">
              <h1 class="heading-title theme-gradient">
                Make things.
              </h1>
              <h2>with the rooster.</h2>
            </div>
          </v-col>
        </v-row>
        <!-- End .row -->
        <!-- Start Service Area  -->
        <div class="service-wrapper service-white">
          <ServiceOne />
        </div>
        <!-- End Service Area  -->
      </v-container>
    </div>
    <!-- End Single Slide  -->
  </div>
  <!-- End Slider Area  -->
</template>

<script>
import ServiceOne from "../../components/service/ServiceOne";
export default {
  components: {
    ServiceOne,
  },
};
</script>

<style scoped>
.theRooster{
  display:flex; 
    
  }
</style>