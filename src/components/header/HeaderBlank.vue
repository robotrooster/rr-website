<template>
  <div>
    <v-navigation-drawer
      class="hidden-md-and-up header-one-page-nav-drawer"
      v-model="drawer"
      fixed
      width="320"
    >
      <v-list-item class="pa-5">
        <div class="logo">
          <!-- <img
            src="../../assets/images/logo/rooster.svg"
            alt="The Rooster"
          /> -->
          <rooster class="theLogoRooster" />
        </div>
        <v-spacer></v-spacer>
        <v-btn
          class="close-icon"
          icon
          @click="drawer = !drawer"
          v-html="iconSvg(closeIcon)"
        >
        </v-btn>
      </v-list-item>
      <scrollactive
        active-class="v-btn--active"
        bezier-easing-value=".5,0,.35,1"
      >
        <v-list>
          <v-list-item
            :ripple="false"
            v-for="item in items"
            :key="item.title"
            :to="item.to"
            link
            class="scrollactive-item"
          >
            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <!-- End mobile menu sidebar item list -->
        </v-list>
      </scrollactive>
    </v-navigation-drawer>
    <!-- End sidebar mobile menu -->

    <v-app-bar
      dark
      color="transparent"
      fixed
      elevate-on-scroll
      class="header-one-page-nav"
    >
      <router-link to="/" class="logo">
        <!-- <slot name="logo"></slot> -->
        <logo class="textLogo" />
        <slot name="logo-dark"></slot>
      </router-link>
      <!-- End brand logo -->
      <v-spacer></v-spacer>
      <v-btn
        icon
        class="ma-0 pa-0 hidden-md-and-up"
        @click="drawer = !drawer"
        v-html="iconSvg(icon)"
      >
      </v-btn>
      <!-- End mobile menu icon -->
      <v-toolbar-items class="hidden-xs-only hidden-sm-only height-auto">
        <scrollactive
          active-class="v-btn--active"
          bezier-easing-value=".5,0,.35,1"
        >
          <v-btn
            v-for="item in items"
            :key="item.title"
            :to="item.to"
            link
            :ripple="false"
            text
            class="scrollactive-item"
            >{{ item.title }}</v-btn
          >
        </scrollactive>

      
       
      </v-toolbar-items>
      <!-- End header menu item -->
    </v-app-bar>
    <!-- End top header navbar -->
  </div>
</template>

<script>
  import feather from "feather-icons";
  import rooster from "../../assets/images/logo/rooster.svg"
  import logo from "../../assets/images/logo/rooster-font-logo.svg"

  export default {
    components:{
      rooster,
      logo
    },
    data: () => ({
      drawer: false,
      items: [
        { title: "Coming Soon", to: "#" },
        // { title: "Service", to: "#service" },
        // { title: "About", to: "#about" },
        // { title: "Portfolio", to: "#portfolio" },
        // { title: "Team", to: "#team" },
        // { title: "Testimonial", to: "#tesimonial" },
        // { title: "Blog", to: "#blog" },
        // { title: "Contact", to: "#contact" }, 
      ],
      icon: "menu",
      closeIcon: "x",
    }),
    methods: {
      iconSvg(icon) {
        return feather.icons[icon].toSvg();
      },
    },
  };
</script>
<style lang="scss">
.theLogoRooster{
  height:7em;
  margin:0 auto;
  margin-left:50%;
  .st0{fill:#574A3F;}
  .st1{fill:#44382C;}
  .st2{fill:#ACA29B;}
  .st3{fill:#D4755D;}
  .st4{fill:#C22026;}
  .st5{fill:#131415;}
  .st6{fill:#ACA29A;}
}
.textLogo{
      .st0{fill:#ACA29A;}
      height: 40px;
      margin: 0 auto;
      position: absolute;
      margin-left: -10em;
      margin-top: -0.75em;
      width: 380px;
    }
    .v-app-bar--is-scrolled .textLogo{
      .st0{fill:#000;}
    }
</style>
