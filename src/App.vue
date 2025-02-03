<template>
  <section class="app-container">
    <appHeader />
    <home />
    <about />
    <gallery />
    <schedule />
    <contact />
    <a class="up-btn on-mobile" @click.prevent="scrollTo('home')"><img src="./assets/imgs/up-arrow.png" alt=""></a>
  </section>
</template>

<script>
import appHeader from './components/appHeader.vue';
import about from './components/about.vue'
import contact from './components/contact.vue'
import gallery from './components/gallery.vue'
import schedule from './components/schedule.vue'
import home from './components/home.vue'

export default {
  data() {
    return {

    }
  },
  methods: {
    scrollTo(id) {
      document.getElementById(id)?.scrollIntoView({ behavior: "smooth" });
    }
  },
  components: {
    appHeader,
    about,
    contact,
    gallery,
    schedule,
    home
  }
}

</script>