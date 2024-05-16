<script>
  import { RouterLink, RouterView } from 'vue-router'
  import AppFooter from './components/AppFooter.vue'
export default{
  components: {
    AppFooter
  },
  data() {
    return {}
  },
}
</script>

<template>
  <header>
   

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav class="flex h-20 w-full px-10 justify-between items-center">
        <figure class="h-full">
          <img class="h-full" src="./assets/_f0628f9d-d773-4d3f-82ea-e4fbde28420d.jpg" alt="">
        </figure>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/faq">FAQ</RouterLink>
        <RouterLink to="/contacts">Contacts</RouterLink>
      </nav>
    </div>
  </header>
  <RouterView />
  <AppFooter></AppFooter>
</template>

<style scoped>

</style>
