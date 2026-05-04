<template>
    <section id="qna" class="faq" style="gap: 10px;">

        <span style="display: flex; align-items: center; gap: 10px;">
            <h3>דברו איתנו</h3>
            <a href="https://wa.me/972527743353" target="_blank">
                <img src="../assets/imgs/whatsapp.svg" alt="WhatsApp" style="height: 60px; width: 60px;">
            </a>
        </span>


        <div class="faq-item" @click="toggleQuestion(index)" v-for="(quest, index) in questions" :key="index">
            <div class="faq-question">
                {{ quest.question }}
            </div>

            <transition name="accordion">
                <div v-if="questionOpen === index" class="faq-answer">
                    {{ quest.answer }}
                </div>
            </transition>
        </div>

    </section>
</template>

<script>
export default {
    name: "GoogleRecommendations",
    data() {
        return {
            questionOpen: null,
            questions: [
                {
                    question: "אני חדשה לחלוטין – מתאים לי?",
                    answer: "לגמרי! רוב האימונים מותאמים לכל רמה – ממתחילות ועד מתאמנות מנוסות."
                },
                {
                    question: "האם האימונים קשים מדי?",
                    answer: "לא! כל אימון מותאם אישית, עם דגש על טכניקה והתקדמות בטוחה."
                },
                {
                    question: "כמה זמן תקפים מסלולי ההיכרות?",
                    answer: `אימון ניסיון – חד פעמי,

3 אימונים ב־99 ₪ – תקף ל־3 שבועות,

מנוי היכרות 8 כניסות – תקף ל־30 יום
`
                },
                {
                    question: "האם מתאים לנשים בהיריון/אחרי לידה?",
                    answer: "כן, ואנחנו נשמח לשוחח איתך כדי להבין מה נכון עבורך"
                },
                {
                    question: "האם אני יכולה להגיע גם לפילאטיס וגם לכוח?",
                    answer: "כן, המנוי כולל פילאטיס מכשירים ואימוני כוח – את בוחרת איך לממש את כל הכניסות שלך, בלי הגבלה על מספר השיעורים מכל סוג."
                },
                {
                    question: "למה הסטודיו לנשים בלבד?",
                    answer: "יצרנו מקום שבו כל אישה תרגיש בנוח, שייכת, ותוכל להתקדם בקצב שלה – ובאווירה נעימה."
                },
            ],
        };
    },
    methods: {
        toggleQuestion(index) {
            this.questionOpen =
                this.questionOpen === index ? null : index;
        },
    },
};
</script>

<style>
.faq {
    max-width: 100%;
    margin: auto;
}

.faq-item {
    cursor: pointer;
    border: 1px solid #ccc;
    border-radius: 15px;
    padding: 1rem;
    width: 100%;
}

.faq-question {
    font-weight: 500;
    font-size: 1.1rem;
}

.faq-answer {
    margin-top: 0.5rem;
    color: #555;
    line-height: 1.6;
}

/* Smooth Animation */
.accordion-enter-active,
.accordion-leave-active {
    transition: all 0.3s ease;
}

.accordion-enter-from,
.accordion-leave-to {
    /* opacity: 0; */
    transform: translateY(-5px);
}
</style>