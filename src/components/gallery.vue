<template>
    <section class="gallery-container" id="gallery">
        <h2>Gallery</h2>

        <ul class="imgs-list">
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
            imgs: Array.from({ length: 9 }, (_, i) => i + 1)
        }
    },
    methods: {
        getImgUrl(img) {
            return `https://res.cloudinary.com/dtgejpwv9/image/upload/v1773246751/Olive/Gallery/gallery-${img}.jpg`
        }
    }
}
</script>