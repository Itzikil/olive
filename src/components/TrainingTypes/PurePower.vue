<template>
    <div class="type-container">

        <div @click="toggleDetails">
            <img src="../../assets/imgs/gym.svg" alt="">
            <h2>Pure power</h2>

            <!-- Toggle Icon -->
            <!-- <span class="arrow" :class="{ open: isOpen }">⌄</span> -->
        </div>

        <!-- <transition name="slide">
            <p v-if="isOpen">
                תוכנית האימונים שלנו לנשים מיועדת לבניית גוף חזק, חטוב ובריא – בדרך אלגנטית ומותאמת אישית.
                בשילוב ציוד מקצועי, הדרכה קשובה ותחושת פרטיות, תוכלי לעבוד על חיזוק הישבן, הירכיים, הבטן והגב – בקצב שלך
                ובנוחות.
                בין אם בשיעור מודרך או באימון עצמאי – כל אימון מקרב אותך לגרסה החזקה והבטוחה יותר של עצמך.
            </p>
        </transition> -->

    </div>
</template>

<script>
export default {
    data() {
        return {
            isOpen: false,
            desc: `אימון כוח קלאסי עם ציוד מקצועי הנותן דגש - טכניקה, זמני מנוחה מסודרים ועליית משקלי עבודה הדרגתית.`,
            highlight: `בניית כוח - חיטוב - חיזוק העצמות - התקדמות עקבית`
        }
    },
    methods: {
        toggleDetails() {
            this.$emit('type-shown', this.desc);
        },
    }
}
</script>