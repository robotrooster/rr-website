<template>
  <div>
  <div v-for="(row, index) in content" :key="index">
    
    <section v-if="row.__component == 'layout.markdown'">
        <vue-markdown :source="row.markdown"/>
    </section>

    <section v-if="row.__component == 'layout.code-block'">
        <vue-code-highlight :language="row.language || 'js'">
            <pre>
              {{row.code}}
          </pre>
          </vue-code-highlight>
      </section>

      <!-- LEFT 50/50 -->
      <section v-if="row.__component == 'layout.50-50-blade' && row.orientation == 'left'">
        <v-row>
            <v-col lg="5" md="5" sm="6" cols="12">
              <img :src="'http://robotrooster.io/api/public'+row.image.url" alt="">
            </v-col>
            <v-col lg="7" md="7" sm="6" cols="12">
              <vue-markdown :source="row.text"/>
            </v-col>
        </v-row>
      </section>

      <!-- RIGHT 50/50 -->
      <section v-if="row.__component == 'layout.50-50-blade' && row.orientation == 'right'">
        <v-row>
            <v-col lg="7" md="7" sm="6" cols="12">
              <vue-markdown :source="row.text"/>
            </v-col>
            <v-col lg="5" md="5" sm="6" cols="12">
              <img :src="'http://robotrooster.io/api/public'+row.image.url" alt="">
            </v-col>
        </v-row>
      </section>

    
    <!-- <div v-else>{{row}}</div>  -->
  
  </div>  
    
  </div>
</template>

<script>
  import VueMarkdown from "vue-markdown-render"
  import {component as VueCodeHighlight} from 'vue-code-highlight';
  import "../../assets/scss/code/vscode.css"

  export default {
    components:{
      VueMarkdown,
      VueCodeHighlight
    },
    props:{
      content:{}
    },
    data() {
      return {
       
      };
    },
  };
</script>
<style lang="scss">
section{
  margin-top:40px;
}
table{
  width:100%;
}
</style>
