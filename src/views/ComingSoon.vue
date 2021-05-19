<template>
  <div>
    <!-- Start Header Area -->
    <HeaderBlank>
      <!-- <img slot="logo" src="../assets/images/logo/rooster-font-logo.svg" /> -->
      <logo slot="logo" class="logo"/>
    </HeaderBlank>
    <!-- End Header Area -->
    <!-- Start 404 Page  -->
    <div class="error-page-inner bg_color--4">
      <v-container>
        <v-row>
          <v-col cols="12">
            <div class="inner">
              <rooster class="theRooster" />
              <h1 class="heading-title theme-gradient">MAKE THINGS</h1>
              <h3 class="sub-title">With the Rooster</h3>
              <v-row class="badge-row">
                
                <v-col cols="4" md="2" sm="3" lg="1">
                  <badge color="#61DAFB" darkColor="#2fcefa" ><react /></badge>
                </v-col>
                <v-col cols="4" md="2" sm="3" lg="1">
                  <badge color="#4FC08D" darkColor="#3aa273"><vuejs /></badge>
                </v-col>
                <v-col cols="4" md="2" sm="3" lg="1">
                  <badge color="#339933" darkColor="#267326"><nodejs /></badge>
                </v-col>  
                <v-col cols="4" md="2" sm="3" lg="1">
                  <badge color="#232F3E" darkColor="#11161d"><aws /></badge>
                </v-col>
                <v-col cols="4" md="2" sm="3" lg="1">
                  <badge color="#21759B" darkColor="#185571"><wordpress /></badge>
                </v-col>
                <v-col cols="4" md="2" sm="3" lg="1">
                  <badge color="#7AB55C" darkColor="#619945"><shopify /></badge>
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

  import react from "../assets/images/brand/react.svg"
  import vuejs from "../assets/images/brand/vue-dot-js.svg"
  import nodejs from "../assets/images/brand/node-dot-js.svg"
  import aws from "../assets/images/brand/amazonaws.svg"
  import wordpress from "../assets/images/brand/wordpress.svg"
  import shopify from "../assets/images/brand/shopify.svg"

  import rooster from "../assets/images/logo/rooster.svg"
  import logo from "../assets/images/logo/rooster-font-logo.svg"
  



  export default {
    components: {
      HeaderBlank,
      FooterTwoTrimmed, 
      Badge,
      react,
      vuejs,
      nodejs,
      aws,
      wordpress,
      shopify,
      rooster,
      logo

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
      right: 1.5em;
      margin: 0 auto;
      height:15em;
      // fill:none;
      .st0{fill:#574A3F;}
        .st1{fill:#44382C;}
        .st2{fill:#ACA29B;}
        .st3{fill:#D4755D;}
        .st4{fill:#C22026;}
        .st5{fill:#131415;}
        .st6{fill:#ACA29A;}
      @media screen and (max-width: 767px){
        font-size: 4em !important;
        height: 2.5em;
        right: 0.3em;
        margin-top: 60px;
        margin-bottom: -0.4em;
      }
      
    }
    
</style>
