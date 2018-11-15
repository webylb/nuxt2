<template>
  <section class="wrap">
    <platformHeader/>
    <div class="testdiv">
      <logo/>
      <h1 class="title">
        goodatall_diy
      </h1>
      <h2 class="subtitle">
        My super-duper Nuxt.js project
      </h2>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          class="button--green">Documentation</a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey">GitHub</a>
      </div>
      <nuxt-link to="/plant">Go to /plant</nuxt-link>
      <nuxt-link to="/mail">Go to /mail</nuxt-link>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'
import platformHeader from '~/components/platformHeader'

export default {
  components: {
    Logo,
    platformHeader
  }
}
</script>

<style lang="less">

.testdiv {
  min-height: 100vh;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
