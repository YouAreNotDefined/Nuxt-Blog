<template>
  <v-app>
    <Header></Header>
    <div class="d-flex mt-10 mb-10 mx-auto" style="max-width: 1300px;">
      <main>
        <Diaries :diaries="diaries"></Diaries>
        <About></About>
      </main>
    </div>
    <Footer></Footer>
  </v-app>
</template>

<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'
import Diaries from '~/components/Diaries.vue'
import About from '~/components/About.vue'

export default {
  async asyncData ({ $content }) {
    const diaries = await $content('diary').fetch()
    return { diaries }
  },
  components: {
    Header,
    Footer,
    Diaries,
    About
  }
}
</script>
