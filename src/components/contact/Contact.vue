<template>
 <div>
      <div class="section-title text-left mb--50 mb_sm--30 mb_md--30">
        <h2 class="contact-heading-title">Make Contact</h2>
        <!-- <p class="description">
          Tell me what you're looking for
        </p> -->
      </div>
      <div class="success-box" v-if="success">
        Your message was sent. <br /> I'll be in touch.
      </div>
       <v-row align="start" class="row--35">
    <v-col lg="6" md="6" sm="6" cols="12" order="2" order-md="1">

        <ValidationObserver v-slot="{ handleSubmit }">
          <form @submit.prevent="handleSubmit(onSubmit)">
            <ValidationProvider
              name="name"
              rules="required"
              v-slot="{ errors }"
            >
              <label>
                <input
                  type="text"
                  v-model="formData.name"
                  placeholder="Your Name *"
                />
                <span class="inpur-error">{{ errors[0] }}</span>
              </label>
            </ValidationProvider>

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
                  placeholder="Your email *"
                />
                <span class="inpur-error">{{ errors[0] }}</span>
              </label>
            </ValidationProvider>

            <ValidationProvider
              name="subject"
              rules="required"
              v-slot="{ errors }"
            >
              <label>
                <input
                  type="text"
                  v-model="formData.subject"
                  placeholder="Write a Subject"
                />
                <span class="inpur-error">{{ errors[0] }}</span>
              </label>
            </ValidationProvider>
        

           
          </form>
        </ValidationObserver>
       
    </v-col>
    <v-col lg="6" md="6" sm="6" cols="12" order="2" order-md="2">
                    <ValidationProvider
                      name="message"
                      rules="required"
                      v-slot="{ errors }"
                    >
                      <label>
                        <textarea
                          v-model="formData.message"
                          placeholder="Your Message"
                        ></textarea>
                        <span class="inpur-error">{{ errors[0] }}</span>
                      </label>
                    </ValidationProvider>
                    
        </v-col>
  </v-row>
        <button
              class="rn-button-style--2 btn_solid"
              type="submit"
              value="submit"
              @click="onSubmit"
            >
              Submit
            </button>
  </div>
</template>

<script>
  import { ValidationObserver } from "vee-validate";
  import { ValidationProvider } from "vee-validate/dist/vee-validate.full.esm";
  import axios from 'axios';
  export default {
    components: {
      ValidationObserver,
      ValidationProvider,
    },
    data() {
      return {
        success:false,
        formData: {
          name: "",
          email: "",
          subject: "",
          message: "",
        },
      };
    },
    methods: {
      onSubmit() {
        axios.post('http://robotrooster.io:3333/contacts',this.formData).then(res=>{
          console.log(res);
          if(res.data.name){
            this.success = true;
            // this.formData = {
            //   name: "",
            //   email: "",
            //   subject: "",
            //   message: "",
            // }
          }
        })
        console.log(this.formData);
      },
    },
  };
</script>
<style lang="scss">
.contact-heading-title{
  font-size:3em !important;
}
.success-box{
    position: relative;
    width: 100%;
    top: -30px;
    margin: 0 auto;
    background: #339933;
    padding: 10px;
    border-radius: 6px;
    color: white;
}
</style>
