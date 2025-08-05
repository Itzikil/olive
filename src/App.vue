<template>
  <section class="app-container">
    <appHeader />
    <home />
    <about />
    <types />
    <schedule />
    <plan/>
    <recommandations />
    <contactForm />
    <gallery />
    <contact />
    <a class="up-btn on-mobile" @click.prevent="scrollTo('home')"><img src="./assets/imgs/up-arrow.png" alt=""></a>
  </section>
</template>

<script>
import appHeader from './components/appHeader.vue';
import home from './components/home.vue'
import about from './components/about.vue'
import types from './components/types.vue'
import schedule from './components/schedule.vue'
import plan from './components/plan.vue'
import recommandations from './components/recommandations.vue'
import contactForm from './components/contactForm.vue'
import gallery from './components/gallery.vue'
import contact from './components/contact.vue'

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
    home,
    about,
    types,
    schedule,
    plan,
    recommandations,
    contactForm,
    gallery,
    contact,
  }
}

</script>