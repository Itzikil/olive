<template>
    <section class="header wide" id="header">
        <div :class="['mobile-menu-container', 'mobile-menu', 'on-mobile', { change: mobileMenu }]" @click="openMenu()">
            <div className="bar1"></div>
            <div className="bar2"></div>
            <div className="bar3"></div>
        </div>
        <div class="logo-container">
            <h2>O-live</h2>
            <img src="../assets/imgs/olive.jpg" alt="logo" class="header-logo">
        </div>
        <nav :class="{ 'close-menu': !mobileMenu }">
            <a @click.prevent="scrollTo('home')">בית</a>
            <a @click.prevent="scrollTo('about')">אודות</a>
            <a @click.prevent="scrollTo('gallery')">גלריה</a>
            <a @click.prevent="scrollTo('schedule')">לוח שיעורים</a>
            <a @click.prevent="scrollTo('contact')">צרו קשר</a>
        </nav>
    </section>
</template>

<script>
export default {
    data() {
        return {
            mobileMenu: false
        }
    },
    methods: {
        scrollTo(id) {
            document.getElementById(id)?.scrollIntoView({ behavior: "smooth" });
        },
        openMenu() {
            this.mobileMenu = !this.mobileMenu
        }
    }
};
</script>
