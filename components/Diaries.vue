<template>
  <ul class="d-flex flex-wrap mx-auto pl-0">
    <li v-for="(diary, index) in diaries" :key="index" class="mr-5 mb-5">
      <v-card
        class="mx-auto"
        max-width="320"
      >
        <v-img
          src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
          height="200px"
        ></v-img>

        <v-card-title>
          {{ diary.title }}
        </v-card-title>

        <v-card-subtitle>
          {{ diary.subtitle }}
        </v-card-subtitle>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            icon
            @click="diary.flag = !diary.flag"
          >
            <v-icon>{{ diary.flag ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
          </v-btn>
        </v-card-actions>

        <v-expand-transition>
          <div v-show="diary.flag">
            <v-divider></v-divider>

            <v-card-text>
              <nuxt-content :document="diary" />
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
  props: { diaries: Array }
})
</script>

<style scoped>
</style>
