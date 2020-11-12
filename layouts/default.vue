<template>
  <v-app>
    <navBar />
    <nuxt />
  </v-app>
</template>

<script>
import navBar from '~/components/navBar'
export default {
  components: {
    navBar
  }
}
</script>
<style >
*{
  margin: 0;
  padding: 0;
}
.large-spacer{
  margin-top: 4rem;
}
</style>
