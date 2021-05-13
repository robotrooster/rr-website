<template>
  <div>
    <!-- Start Header Area -->
    <HeaderBlank>
      <img slot="logo" src="../assets/images/logo/rooster-font-logo.svg" />
    </HeaderBlank>
    <!-- End Header Area -->
    <!-- Start 404 Page  -->
    <div class="error-page-inner bg_color--4">
      <v-container>
        <v-row>
          <v-col cols="12">
            <div class="inner">
              <img src="../assets/images/logo/rooster.svg" class="theRooster">
              <h1 class="heading-title theme-gradient">MAKE THINGS</h1>
              <h3 class="sub-title">With the Rooster</h3>
              <!-- <span>This site is brand new, and should be fully operational by summer 2021</span> -->
              <div class="error-button">
                <!-- <router-link class="rn-button-style--2 btn_solid" to="/"
                  >Back To Homepage</router-link
                > -->
              </div>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>
    <FooterTwoTrimmed />
  </div>
</template>

<script>
  import HeaderBlank from "../components/header/HeaderBlank";
  import FooterTwoTrimmed from "../components/footer/FooterTwoTrimmed";
  export default {
    components: {
      HeaderBlank,
      FooterTwoTrimmed, 
    },
    data() {
      return {};
    },
  };
</script>
<style lang="scss">
  .heading-title{
    font-size:10em !important;
    line-height: 50px;
      @media screen and (max-width: 767px){
        font-size: 4em !important;
        line-height: 1.2;
        margin-top: 30px;
      }
    }
  .theRooster{
      text-align: center;
      margin: 0 auto;
      height:25em;
      @media screen and (max-width: 767px){
        font-size: 4em !important;
        height:3.5em;
        margin-top: 30px;
      }
    }
</style>
