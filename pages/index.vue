<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        nuxt-fundamentals
      </h1>
      <h2 class="subtitle">
        My lovely Nuxt.js project
      </h2>
      <div class="links">
        <nuxt-link v-for="post in posts" :key="post.id" :to="`posts/${post.id}`" class="button--grey">{{post.title}}</nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  head () {
    return {
      title: 'Home | Nuxt course on vueschool',
      meta: [
        { name: 'twitter:title', content: 'Nuxt Fundamentals by VueSchool' },
        { name: 'twitter:description', conent: 'Nuxt + Vueschool = 🍕' },
        { name: 'twitter:image', content: 'https://i.imgur.com/UYP2umJ.png' },
        { name: 'twitter:card', content: 'summary_large_image' }
      ]
    }
  },
  computed: {
    posts () {
      return this.$store.state.posts.all
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
  'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  letter-spacing: 1px;
}
.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
}
.links {
  padding-top: 15px;
}
</style>
