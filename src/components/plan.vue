<template>
    <section id="plan" class="plan-container">
        <h2 class="section-title">בחרי את התוכנית שמתאימה לך</h2>

        <div class="plans-wrapper">
            <div class="plan-item" v-for="plan in getPlans()" :key="plan.id" :class="plan.class">
                <h3>{{ plan.title }}</h3>
                <p class="description">{{ plan.description }}</p>
                <ul>
                    <li v-for="(feature, i) in plan.features" :key="i">
                        <div class="dot"></div> {{ feature }}
                    </li>
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
                    title: " 🌿 שיעור נסיון",
                    description: " להגיע, להתנסות, להרגיש את האווירה והאימון.",
                    features: [
                        "שיעור ניסיון חד פעמי",
                        "היכרות עם האווירה",
                    ],
                    price: " 50 ₪"
                },
                {
                    id: "guided",
                    class: "guided",
                    title: "🌿 חבילת היכרות",
                    description: "שיעורים קבוצתיים אינטימיים בהדרכת מדריכה מוסמכת, לחיזוק, גמישות ותחושת רוגע.",
                    features: [
                        "תקף ל־3 שבועות מרגע הרכישה.",
                        "מאפשר להכיר כמה סוגי אימונים.",
                    ],
                    price: "3 אימונים ב 99 ₪"
                },
                {
                    id: "premium",
                    class: "premium",
                    title: "🌿 מנוי היכרות",
                    description: "השילוב המושלם בין עצמאות, הדרכה וליווי אישי. למי שרוצה להתחייב לתהליך אמיתי ולראות שינוי.",
                    features: [
                        "8 כניסות",
                        "תקף ל־30 יום",
                        "מסגרת התחלתית עם ליווי ויחס אישי",
                    ],
                    price: "349 ₪"
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