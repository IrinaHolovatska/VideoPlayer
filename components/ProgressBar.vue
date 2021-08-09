<template>
  <v-container>
    <v-progress-linear
        background-opacity="0.5"
        rounded
        class="progressLinear"
        value="10"
        height="6px"
        background-color='rgb(130, 39, 159)'
        v-model="valueDeterminate">
    </v-progress-linear>
  </v-container>
</template>

<script>
export default {
  name: "ProgressBar",
  data() {
    return {
      valueDeterminate: 50,
    }
  },
}
</script>

<style scoped>
.v-progress-linear {
  background-color: rgb(235, 238, 245);
}

</style>