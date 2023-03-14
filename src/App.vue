<script >
import ProjectMain from './components/ProjectMain.vue';
import AppHeader from './components/AppHeader.vue';

export default {
  components: {
    ProjectMain,
    AppHeader,

  },
  data() {
    return {

    }
  }
}
</script>

<template>
  <AppHeader />
  <!-- <ProjectMain /> -->
  <router-view />
</template>

<style lang="scss">
@use "./styles/generals.scss" as *;
</style>
