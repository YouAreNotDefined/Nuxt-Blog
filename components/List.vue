<template>
  <ul class="d-flex flex-wrap mx-auto pl-0">
    <li v-for="(article, index) in articles" :key="index" class="mr-4 mb-5">
      <v-card
        class="mx-auto"
        width="300"
      >
        <v-card-text>
          <time :datetime="article.date.replace(/\./g,'-')">{{ article.date }}</time>
          <p class="headline text--primary">
            {{ article.title }}
          </p>
          <div class="white--text light-green darken-1 px-2 font-weight-light d-inline-block">{{ article.category }}</div>
          <div class="text--primary mt-3">
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
