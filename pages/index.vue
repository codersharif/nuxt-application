<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <div class="text-center">
        <!-- <logo /> -->
        <vuetify-logo />
      </div>
      <v-card>
        <v-card-title class="headline">
          Welcome to the Vuetify + Nuxt.js template
        </v-card-title>
        <v-card-actions>
          <v-spacer />
          <nuxt-link  v-for="post in posts" :key="post.id" :to="{name: 'posts-id', params: {id: post.id}}">{{post.title}}</nuxt-link>

        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
// import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    // Logo,
    VuetifyLogo,
  },
  computed:{
    posts(){
      return this.$store.state.posts.all;
    }
  }
}
</script>
