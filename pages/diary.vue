<template>
  <v-app>
    <Header></Header>
    <div class="d-flex mt-10 mb-10 mx-auto" style="max-width: 1300px;">
      <Diaries></Diaries>
      <About></About>
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
  components: {
    Header,
    Footer,
    Diaries,
    About
  }
}
</script>
