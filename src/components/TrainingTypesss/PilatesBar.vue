<template>
    <div class="type-container">

        <div @click="toggleDetails">
            <!-- <img src="../../assets/imgs/pilates.svg" alt=""> -->
            <h2>Pilates bar</h2>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isOpen: false,
            desc: `3תוכנית האימונים שלנו לנשים מיועדת לבניית גוף חזק, חטוב ובריא – בדרך אלגנטית ומותאמת אישית.
             בשילוב ציוד מקצועי, הדרכה קשובה ותחושת פרטיות, 
             תוכלי לעבוד על חיזוק הישבן, הירכיים, הבטן והגב – בקצב שלך ובנוחות.
              בין אם בשיעור מודרך או באימון עצמאי – כל אימון מקרב אותך לגרסה החזקה והבטוחה יותר של עצמך.`
        }
    },
    methods: {
        toggleDetails() {
            this.$emit('type-shown', this.desc);
        },
    }
}
</script>