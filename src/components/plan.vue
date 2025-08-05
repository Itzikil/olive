<template>
    <section id="plan" class="plan-container">
        <h2 class="section-title">בחרי את התוכנית שמתאימה לך</h2>

        <div class="plans-wrapper">
            <div class="plan-item" v-for="plan in getPlans()" :key="plan.id" :class="plan.class">
                <h3>{{ plan.title }}</h3>
                <p class="description">{{ plan.description }}</p>
                <ul>
                    <li v-for="(feature, i) in plan.features" :key="i">✅ {{ feature }}</li>
                </ul>
                <p class="price">{{ plan.price }}</p>
                <button @click="selectPlan(plan.id)">הצטרפי עכשיו</button>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: "PricingPlans",
    methods: {
        getPlans() {
            return [
                {
                    id: "basic",
                    class: "basic",
                    title: "תכנית בסיסית",
                    description: "גישה חופשית לאימונים עצמיים בסטודיו, לפי שעות פתיחה. מושלם למי שמעדיפה להתאמן לבד, בשקט ובקצב אישי.",
                    features: [
                        "גישה חופשית לסטודיו",
                        "ייעוץ פתיחה עם מדריכה",
                        "גמישות מלאה – ללא התחייבות"
                    ],
                    price: "₪250 לחודש"
                },
                {
                    id: "guided",
                    class: "guided",
                    title: "תכנית מודרכת",
                    description: "שיעורים קבוצתיים אינטימיים בהדרכת מדריכה מוסמכת, לחיזוק, גמישות ותחושת רוגע.",
                    features: [
                        "2-3 שיעורים בשבוע",
                        "גישה גם לאימונים עצמיים",
                        "קבוצות קטנות ואווירה יוקרתית"
                    ],
                    price: "₪390 לחודש"
                },
                {
                    id: "premium",
                    class: "premium",
                    title: "תכנית פרימיום",
                    description: "השילוב המושלם בין עצמאות, הדרכה וליווי אישי. למי שרוצה להתחייב לתהליך אמיתי ולראות שינוי.",
                    features: [
                        "שיעורים מודרכים ללא הגבלה",
                        "כניסה חופשית לאימונים עצמיים",
                        "תכנית מותאמת אישית ומעקב חודשי",
                        "עדיפות בהרשמה לשיעורים"
                    ],
                    price: "₪490 לחודש"
                }
            ];
        },
        selectPlan(planId) {
            console.log(`Selected plan: ${planId}`);
            // Future logic: navigate, store, or show form
        }
    }
};
</script>