<template>
  <div class="white elevation-2">
    <v-toolbar flat dense class="blue-grey darken-1" dark>
      <v-toolbar-title>
        {{title}}
      </v-toolbar-title>
      <slot name="action" />
    </v-toolbar>
    <div class="pl-4 pr-4 pt-2 pb-2">
      <slot>
        No content
      </slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ['title']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
