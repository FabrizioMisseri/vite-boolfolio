<script>
import AppMain from './components/AppMain.vue';

export default {
  name: 'app',

  components: {
    AppMain,
  }
}
</script>

<template>
  <AppMain />
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
</style>
