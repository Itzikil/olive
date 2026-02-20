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
            <a @click.prevent="scrollTo('about')">עלינו</a>
            <a @click.prevent="scrollTo('gallery')">גלריה</a>
            <a @click.prevent="scrollTo('types')">סוגי אימון</a>
            <a @click.prevent="scrollTo('schedule')">מערכת שעות</a>
            <a @click.prevent="scrollTo('plan')">מסלולים</a>
            <!-- <a @click.prevent="scrollTo('home')">הטבה למצטרפות חדשות</a> -->
            <a @click.prevent="scrollTo('recommandations')">המלצות</a>
            <a @click.prevent="scrollTo('contactForm')">השארת פרטים</a>
            <a @click.prevent="scrollTo('contact')">צרו קשר</a>
            <div class="link-container">
                <a target="_blank" href="https://www.facebook.com/profile.php?id=61563921330158"><img class="logo"
                        src="@/assets/imgs/facebook.svg" alt="facebook"></a>
                <a target="_blank" href="https://www.instagram.com/o_live_studio/"><img class="logo"
                        src="@/assets/imgs/instagram.svg" alt="youtube"></a>
            </div>
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
        // scrollTo(id) {
        //     document.getElementById(id)?.scrollIntoView({ behavior: "smooth" });
        // },
        scrollTo(id) {
            const el = document.getElementById(id);
            if (el) {
                const headerOffset = 80; // change this to your header's actual height in pixels
                const elementPosition = el.getBoundingClientRect().top + window.pageYOffset;
                const offsetPosition = elementPosition - headerOffset;

                window.scrollTo({
                    top: offsetPosition,
                    behavior: "smooth"
                });
            }
        },
        openMenu() {
            this.mobileMenu = !this.mobileMenu
        }
    }
};
</script>
