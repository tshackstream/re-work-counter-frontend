<template>
  <v-app dark>
    <v-main>
      <nuxt></nuxt>
      <v-footer></v-footer>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'

@Component
export default class simple extends Vue {}
</script>

<style scoped></style>
