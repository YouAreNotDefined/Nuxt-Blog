<template>
  <v-app>
    <Header></Header>
    <List></List>
    <Footer></Footer>
  </v-app>
</template>

<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'
import List from '~/components/List.vue'

export default {
  components: {
    Header,
    Footer,
    List
  }
}
</script>
