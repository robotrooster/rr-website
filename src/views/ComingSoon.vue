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
              <v-row class="badge-row">
                
                <v-col cols="4" md="2" sm="3" lg="1">
                  <badge symbol="../../images/brand/react.svg" color="#61DAFB" darkColor="#2fcefa" />
                </v-col>
                <v-col cols="4" md="2" sm="3" lg="1">
                  <badge symbol="../../images/brand/vue-dot-js.svg" color="#4FC08D" darkColor="#3aa273" />
                </v-col>
                <v-col cols="4" md="2" sm="3" lg="1">
                  <badge symbol="../../images/brand/node-dot-js.svg" color="#339933" darkColor="#267326" />
                </v-col>  
                <v-col cols="4" md="2" sm="3" lg="1">
                  <badge symbol="../../images/brand/amazonaws.svg" color="#232F3E" darkColor="#11161d" />
                </v-col>
                <v-col cols="4" md="2" sm="3" lg="1">
                  <badge symbol="../../images/brand/wordpress.svg" color="#21759B" darkColor="#185571" />
                </v-col>
                <v-col cols="4" md="2" sm="3" lg="1">
                  <badge symbol="../../images/brand/shopify.svg" color="#7AB55C" darkColor="#619945" />
                </v-col>
              </v-row>
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
  import Badge from "../components/brand/Badge"



  export default {
    components: {
      HeaderBlank,
      FooterTwoTrimmed, 
      Badge

    },
    data() {
      return {};
    },
  };
</script>
<style lang="scss">
.badge-row{
  margin-top:25px;
  justify-content: center;
}
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
      position:relative;
      right: 3.5em;
      margin: 0 auto;
      height:25em;
      @media screen and (max-width: 767px){
        font-size: 4em !important;
        height:3.5em;
        right:0.5em;
        margin-top: 30px;
      }
    }
</style>
