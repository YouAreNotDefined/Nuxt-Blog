<template>
  <v-app>
    <Header></Header>
    <main class="d-flex mt-10 mb-10 mx-auto main">
      <List :articles="articles"></List>
      <About></About>
    </main>
    <Footer></Footer>
  </v-app>
</template>

<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'
import List from '~/components/List.vue'
import About from '~/components/About.vue'

export default {
  async asyncData ({ $content }) {
    const articles = await $content('article').fetch()
    return { articles }
  },
  components: {
    Header,
    Footer,
    List,
    About
  }
}
</script>
