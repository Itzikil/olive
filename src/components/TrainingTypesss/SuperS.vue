<template>
    <div class="type-container">

        <div @click="toggleDetails">
            <!-- <img src="../../assets/imgs/gym.svg" alt=""> -->
            <h2>Super S</h2>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isOpen: false,
            desc: `אימון כוח דינמי הבנוי כולו מסופר סטים בשילוב ציוד מקצועי.
אימון מאתגר בקצב גבוה! 
בניית כוח - חיטוב - שיפור סיבולת
`}
    },
    methods: {
        toggleDetails() {
            this.$emit('type-shown', this.desc);
        },
    }
}
</script>