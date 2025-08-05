<template>
    <section class="gallery-container" id="gallery">
        <h2>Gallery</h2>
        <ul class="imgs-list">
            <li v-for="img in imgs">
                <img src="../assets/imgs/gallery-1.jpg" alt="">
            </li>
        </ul>
    </section>
</template>

<script>
export default {
    data() {
        return {
            imgs: [1, 2, 3, 4, 5, 6, 7, 8]
        }
    }
}
</script>