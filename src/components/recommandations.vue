<template>
    <section id="recommandations" class="recommandations-container">
        <h2>המלצות</h2>
        <ul class="rec-container">
            <li v-for="img in imgs" :key="img">
                <img :src="getImgUrl(img)" alt="" :class="img === '3' ? 'rounded' : ''"/>
            </li>
        </ul>
    </section>
</template>


<script>
export default {
    data() {
        return {
            imgs: ["1", "2", "3", "4", "5", "6", "7", "8", "9", "10", "11", "12", "13", "14", "15", "16", "17", "18", "19", "20", "21", "22"]
        }
    },
    methods: {
        getImgUrl(img) {
            return new URL(
                `../assets/imgs/recommendations/rec${img}.jpg`,
                import.meta.url
            ).href
        },
    }
}
</script>