<template>
  <div>
    <div id="wrapper">
      <Sidebar :data-toggle="data.dataToggles" @action="toggle()" />
      <div id="content" :class="{ 'content-leaderboard': $route.name == 'leaderboard', 'active': !data.dataToggles }">
        <nuxt />
        <Footer />
      </div>
      <SidebarRight v-if="$route.name != 'leaderboard'" />
      <div class="overlay" :class="data.dataToggles ? 'active' : ''" @click="hideSidebar()" />
    </div>
  </div>
</template>

<script>
import Sidebar from '~/components/Sidebar.vue'
import SidebarRight from '~/components/SidebarRight.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    Sidebar,
    SidebarRight,
    Footer
  },
  data () {
    return {
      data: {
        dataToggles: false
      }
    }
  },
  methods: {
    hideSidebar () {
      this.data.dataToggles = false
    },
    toggle () {
      this.data.dataToggles = !this.data.dataToggles
    }
  }
}
</script>
