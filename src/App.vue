<script>
import AppHeader from './components/AppHeader.vue';

export default {
  name: 'app',

  components: {
    AppHeader,
  }
}
</script>

<template>
  <AppHeader />
  <router-view></router-view>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
</style>
