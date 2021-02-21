<template>
  <v-app>
    <Header></Header>
    <main class="main mx-auto d-flex">
      <v-card
        class="mr-5"
        color="#00000"
        width="1000"
      >
        <v-card-text class="font-weight-bold d-flex pb-0">
          <time :datetime="transDate">{{ article.date }}</time>
          <div class="ml-3 white--text light-green darken-1 px-2 font-weight-light">{{ article.category }}</div>
        </v-card-text>
        <v-card-title class="font-weight-bold">
          <h1 class="display-1">{{ article.title }}</h1>
        </v-card-title>
        <v-card-text class="font-weight-bold">
          <nuxt-content :document="article" />
        </v-card-text>
      </v-card>
      <About></About>
    </main>
    <Footer></Footer>
  </v-app>
</template>

<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'
import About from '~/components/About.vue'

export default {
  components: {
    Header,
    Footer,
    About
  },
  async asyncData ({ $content, params }) {
    const article = await $content('article', params.slug).fetch()
    return { article }
  },
  computed:{
    transDate(){
      return this.article.date.replace(/\./g,'-');
    }
  }
}
</script>

<style scoped>
@media screen and (min-width: 767px) {
  .article-main{
    width: 1000px;
    margin-right: 20px;
  }
}

@media screen and (max-width: 768px) {

}
</style>
