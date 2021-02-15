<template>
  <ul class="d-flex flex-wrap mx-auto">
    <li v-for="(array, index) in data" :key="index" class="mr-4 mb-4">
      <v-card
        class="mx-auto"
        max-width="320"
      >
        <v-img
          src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
          height="200px"
        ></v-img>

        <v-card-title>
          Top western road trips
        </v-card-title>

        <v-card-subtitle>
          1,000 miles of wonder
        </v-card-subtitle>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            icon
            @click="array.flag = !array.flag"
          >
            <v-icon>{{ array.flag ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
          </v-btn>
        </v-card-actions>

        <v-expand-transition>
          <div v-show="array.flag">
            <v-divider></v-divider>

            <v-card-text>
              I'm a thing. But, like most politicians, he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.
            </v-card-text>
          </div>
        </v-expand-transition>
      </v-card>
    </li>
  </ul>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data(){
    return {
      show: false,
      data: [
        { flag: false, num: 0 },
        { flag: false, num: 1 },
        { flag: false, num: 2 },
        { flag: false, num: 3 },
        { flag: false, num: 4 },
        { flag: false, num: 5 }
      ]
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
