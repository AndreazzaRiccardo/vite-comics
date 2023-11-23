<script>
import AppHeader from "./components/AppHeader.vue"
import AppMain from "./components/AppMain.vue"
import AppAd from "./components/AppAd.vue"
import AppFooter from "./components/AppFooter.vue"
export default {
  components: {
    AppHeader,
    AppMain,
    AppAd,
    AppFooter
  },
  data() {
    return {

    }
  }
}
</script>

<template>
  <AppHeader/>
  <AppMain/>
  <AppAd/>
  <AppFooter/>
</template>

<style lang="scss">

</style>
