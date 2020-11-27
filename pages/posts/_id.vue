<template>
  <v-row>
    <v-col class="text-center col-md-6">
      <img src="/v.png" alt="Vuetify.js" class="mb-5" />
      <v-card>
        <v-card-title>
          {{post.title}}
        </v-card-title>
        <v-card-text>
            {{post.content}}
        </v-card-text>
      </v-card>
    </v-col>
    <v-col class="col-md-6">
     <ul>
       <li v-for="(related,i) in relatedPost" :key="i">
         <!-- system-1 -->
         <!-- <nuxt-link :to="`/posts/${related.id}`">{{related.title}}</nuxt-link> -->

         <!-- system-2 -->
         <nuxt-link :to="{name: 'posts-id', params: {id: related.id}}">{{related.title}}</nuxt-link>
         </li>
     </ul>
    </v-col>
  </v-row>
</template>
<script>
export default {
  data(){
    return{
      id:this.$route.params.id,
      // posts:[]
    }
  },
  computed:{
    post(){
      // return this.posts.find(post => post.id === this.id);
      return this.$store.state.posts.all.find(post => post.id === this.id);
    },
    relatedPost(){
      // return this.posts.filter(post => post.id !== this.id);
      return this.$store.state.posts.all.filter(post => post.id !== this.id);
    }

  }
}
</script>