<template>
  <div>
    <!-- Start Header Area -->
    <HeaderBlank>
      <img slot="logo" src="../../assets/images/logo/rooster-font-logo.svg" /> 
    </HeaderBlank>
    <!-- End Header Area -->

    <!-- Start Breadcrump Area  -->
    <div
      class="rn-page-title-area pt--120 pb--190 bg_image bg_image--7"
      data-black-overlay="7"
    >
      <v-container>
        <v-row>
          <v-col cols="12">
            <div class="blog-single-page-title text-center pt--100">
              <h2 class="heading-title theme-gradient">
                {{blogData.title}}
              </h2>
              <ul class="blog-meta d-flex justify-center align-center">
                <li class="d-flex" v-for="(meta, i) in metaList" :key="i">
                  <span v-html="iconSvg(meta.icon)"></span>{{ meta.text }}
                </li>
              </ul>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>
    <!-- End Breadcrump Area  -->

    <!-- Start Blog Details Area  -->
    <div class="rn-blog-details pt--110 pb--70 bg_color--1">
      <v-container>
        <v-row>
          <v-col cols="12">
            <div class="inner-wrapper">
              <div class="inner">

                <content-render :content="blogBody"></content-render>
              
            </div>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>
    <!-- End Blog Details Area  -->

    <!-- Start Comment Form  -->
    <div class="blog-comment-form pb--120 bg_color--1">
      <v-container>
        <v-row>
          <v-col cols="12">
            <div class="inner">
              <h3 class="title mb--40 fontWeight500">Leave a Reply</h3>
              <ValidationObserver v-slot="{ handleSubmit }">
                <form @submit.prevent="handleSubmit(onSubmit)">
                  <v-row>
                    <v-col lg="6" md="12" cols="12">
                      <div class="rnform-group">
                        <ValidationProvider
                          name="name"
                          rules="required"
                          v-slot="{ errors }"
                        >
                          <label>
                            <input
                              type="text"
                              v-model="formData.name"
                              placeholder="Name"
                            />
                            <span class="inpur-error">{{ errors[0] }}</span>
                          </label>
                        </ValidationProvider>
                      </div>
                      <div class="rnform-group">
                        <ValidationProvider
                          name="email"
                          rules="required|email"
                          v-slot="{ errors }"
                        >
                          <label>
                            <input
                              type="text"
                              rules="required|email"
                              v-model="formData.email"
                              placeholder="Email"
                            />
                            <span class="inpur-error">{{ errors[0] }}</span>
                          </label>
                        </ValidationProvider>
                      </div>
                      <div class="rnform-group">
                        <ValidationProvider
                          name="website"
                          rules="required"
                          v-slot="{ errors }"
                        >
                          <label>
                            <input
                              type="text"
                              v-model="formData.subject"
                              placeholder="Website"
                            />
                            <span class="inpur-error">{{ errors[0] }}</span>
                          </label>
                        </ValidationProvider>
                      </div>
                    </v-col>
                    <v-col lg="6" md="12" cols="12">
                      <div class="rnform-group">
                        <ValidationProvider
                          name="comment"
                          rules="required"
                          v-slot="{ errors }"
                        >
                          <label>
                            <textarea
                              v-model="formData.message"
                              placeholder="Comment"
                            ></textarea>
                            <span class="inpur-error">{{ errors[0] }}</span>
                          </label>
                        </ValidationProvider>
                      </div>
                    </v-col>
                    <v-col cols="12">
                      <div class="blog-submit-btn">
                        <button
                          class="rn-button-style--2 btn_solid"
                          type="submit"
                          value="submit"
                        >
                          SEND MESSAGE
                        </button>
                      </div>
                    </v-col>
                  </v-row>
                </form>
              </ValidationObserver>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>
    <!-- End Comment Form  -->

    <FooterTwoTrimmed />
  </div>
</template>

<script>
  import HeaderBlank from "../../components/header/HeaderBlank";
  import FooterTwoTrimmed from "../../components/footer/FooterTwoTrimmed";
  import feather from "feather-icons";
  import axios from "axios";
  import ContentRender from "../../components/blog/ContentRender"


  import { ValidationObserver } from "vee-validate";
  import { ValidationProvider } from "vee-validate/dist/vee-validate.full.esm";

  export default {
    components: {
      HeaderBlank,
      ContentRender,
      FooterTwoTrimmed,
      ValidationObserver,
      ValidationProvider
    },
    props:{
      postId: {
        type: String,
        required: false
      }
  },
    data() {
      return {
        blogData:{},
        blogBody:"",
        formData: {
          name: "",
          email: "",
          subject: "",
          message: "",
        },
        items: [
          {
            thumb: require("../../assets/images/blog/bl-big-01.jpg"),
            src: "https://www.youtube.com/watch?v=ZOoVOfieAF8",
          },
        ],
        metaList: [
          {
            icon: "clock",
            text: "May 18, 2020",
          },
          {
            icon: "user",
            text: "Fatima",
          },
          {
            icon: "message-circle",
            text: "15 Comments",
          },
          {
            icon: "heart",
            text: "Like",
          },
        ],
        index: null,
      };
    },
    mounted(){
      this.getBlogPost()
    },

    methods: {
      getBlogPost(){
        console.log("POST ID:", this.postId)
        axios.get("http://robotrooster.io:3333/posts/" + this.postId).then(res=>{
          console.log("returned:",res);
          this.blogData = res.data;
          this.blogBody = res.data.body;
        })
      },

      iconSvg(icon) {
        return feather.icons[icon].toSvg();
      },
      onSubmit() {
        console.log(this.formData);
      },
    },
  };
</script>
