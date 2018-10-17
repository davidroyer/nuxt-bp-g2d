<template>
  <nav role="navigation"
       class="nav desktop-nav"
       itemscope
       itemtype="http://schema.org/SiteNavigationElement">
    <ul class="nav-list desktop-nav-list">
      
      <nuxt-link
        v-for="(item, index) in menuItems"
        :to="handleSlug(item)" 
        :key="index"
        class="desktop-nav-item"
        tag="li">
        <a itemprop="url">
          <span itemprop="name" 
                v-text="item.title"/>
        </a>
      </nuxt-link>
  </ul></nav>
</template>

<script>
export default {
  computed: {
    menuItems () {
      return this.$store.getters.menuItems
    },    
  },
  methods: {
    handleSlug (menuItem) {
      const { url } = menuItem
      const siteUrl = `${this.$store.state.siteData.home}/`
      if (url === this.$store.state.siteData.url) return '/'
      else return url.replace(siteUrl, '/')
    }
  }  
}
</script>


<style scoped>
.nav-list {
  @apply list-reset;
}
</style>

<style lang="scss" scoped>
.desktop-nav {
    display: none;
  
  @media (min-width: 900px) {
    display: block;
  }
  &-list {
    margin-bottom: 0;
    display: flex;
  }
  &-item {
    list-style-type: none;
    margin-bottom: 0;
  }
}

.drawerToggle {
  -webkit-appearance: none;
  cursor: pointer;
  background: white;
  border: none;
  font-size: 1em;
  font-weight: 400;
  font-family: Vollkorn, sans-serif;
  position: relative;
  z-index: 9;
}
  @media (min-width: 900px) {
    .drawerToggle, .v-menu-button {
      display: none;
    }
  }
header {
  display: flex;
  align-items: center;
  justify-content: space-around;
  justify-content: space-between;
  padding: 0 1.25em;
  .logo {
    width: 125px;
    margin: 0;
  }
}

nav {
  a {
    color: white;
    margin: 0.25em 0.75em;
  }
}
</style>