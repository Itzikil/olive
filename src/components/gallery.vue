<template>
    <section class="gallery-container" id="gallery">
        <h2>Gallery</h2>

        <ul class="imgs-list">
            <li v-for="img in imgs" :key="img">
                <img :src="getImgUrl(img)" alt="" />
            </li>
            <li v-for="img in imgs" :key="img">
                <img :src="getImgUrl(img)" alt="" />
            </li>
            <li v-for="img in imgs" :key="img">
                <img :src="getImgUrl(img)" alt="" />
            </li>
        </ul>
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
                `../assets/imgs/gallery/${img}.jpg`,
                import.meta.url
            ).href
        }
    }
}
</script>