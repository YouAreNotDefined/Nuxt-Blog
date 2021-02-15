<template>
  <ul class="d-flex flex-wrap mx-auto">
    <li v-for="(num, index) in nums" :key="index" class="mr-4 mb-4">
      <v-card
        class="mx-auto"
        max-width="345"
      >
        <v-card-text>
          <div>Word of the Day {{ num }}</div>
          <p class="display-1 text--primary">
            be•nev•o•lent
          </p>
          <p>adjective</p>
          <div class="text--primary">
            well meaning and kindly.<br>
            "a benevolent smile"
          </div>
        </v-card-text>
        <v-card-actions>
          <v-btn
            text
            color="deep-purple accent-4"
          >
            Learn More
          </v-btn>
        </v-card-actions>
      </v-card>
    </li>
  </ul>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data(){
    return {
      nums: [0,1,2,3,4,5,6,7]
    }
  },
  async asyncData ({ $content, params }) {
    const query = await $content('articles').limit(15)
    const articles = await query.fetch()
    return { articles }
  }
})
</script>

<style scoped>
</style>
