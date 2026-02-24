<template>
    <section id="recommandations" class="recommandations-container">
        <h2>המלצות</h2>
        <!-- <ul class="imgs-list">
            <li v-for="img in imgs" :key="img">
                <img :src="getImgUrl(img)" alt="" />
            </li>
        </ul> -->
        <div class="rec-container imgs-list">
            <img src="../assets/imgs/whatsapp.avif" alt="">
            <img src="../assets/imgs/whatsapp.avif" alt="">
            <img src="../assets/imgs/whatsapp.avif" alt="">
            <img src="../assets/imgs/whatsapp.avif" alt="">
            <img src="../assets/imgs/whatsapp.avif" alt="">
            <img src="../assets/imgs/whatsapp.avif" alt="">
        </div>
    </section>
</template>


<script>
export default {
    data() {
        return {
            imgs: ["1", "2", "3", "4", "5", "6", "7"]
        }
    },
    methods: {
        getImgUrl(img) {
            return new URL(
                `../assets/imgs/recommands/${img}.jpg`,
                import.meta.url
            ).href
        }
    }
}
</script>