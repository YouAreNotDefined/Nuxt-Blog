<template>
  <ul class="d-flex flex-wrap mx-auto pl-0">
    <li v-for="(article, index) in articles" :key="index" class="mr-4 mb-5">
      <v-card
        class="mx-auto"
        max-width="345"
      >
        <v-card-text>
          <div>{{ article.date }}</div>
          <p class="display-1 text--primary">
            {{ article.title }}
          </p>
          <p>{{ article.category }}</p>
          <div class="text--primary">
            {{ article.description }}
          </div>
        </v-card-text>
        <v-card-actions>
          <nuxt-link :to="article.path">
            <v-btn
              text
              color="deep-purple accent-4"
            >
              Learn More
            </v-btn>
          </nuxt-link>
        </v-card-actions>
      </v-card>
    </li>
  </ul>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: { articles: Array }
})
</script>

<style scoped>
</style>
