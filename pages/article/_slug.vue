<template>
  <v-app>
    <Header></Header>
    <h1>{{ article.title }}</h1>
    <nuxt-content :document="article" />
    <Footer></Footer>
  </v-app>
</template>

<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    Header,
    Footer
  },
  async asyncData ({ $content, params }) {
    const article = await $content('article', params.slug).fetch()
    return { article }
  }
}
</script>
