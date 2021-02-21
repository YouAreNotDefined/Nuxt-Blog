<template>
  <header class="text-center pb-7 pt-7 d-flex mx-auto justify-space-between" style="width: 1200px;">
    <v-hover v-slot="{ hover }">
      <h1 class="mr-10" :class="{ 'on-hover': hover }">
        <router-link to="/" class="black--text"><img src="" alt="Bouzuweed"></router-link>
      </h1>
    </v-hover>
    <v-hover v-slot="{ hover }">
      <router-link to="/diary" class="text-right black--text" :class="{ 'on-hover': hover }">Diary</router-link>
    </v-hover>
  </header>
</template>
