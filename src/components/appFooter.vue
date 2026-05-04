<template>
    <section class="footer-container wide">
        <a href="https://wa.me/972527743353" target="_blank" class="footer-whatsapp" style="height: 30px; width: 30px;">
            <img src="../assets/imgs/whatsapp.svg" alt="whatsApp" style="height: 30px; width: 30px;">
        </a>
        <a @click.prevent="scrollTo('plan')" class="footer-text">הרשמה להיכרות</a>
    </section>
</template>


<script>
export default {
    methods: {
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
    }
};
</script>
