<template>
    <section id="plan" class="plan-container">
        <h2 class="section-title">אופציות היכרות שלנו</h2>
        <p>בחרי את דרך ההיכרות שמתאימה לך</p>
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
                <button @click="selectPlan(plan.id)">
                    <a :href="plan.link" target="_blank">הצטרפי עכשיו</a>
                </button>
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
                    title: " 🌿 אימון נסיון",
                    description: " כניסה חד פעמי לאימון כוח או פילאטיס מכשירים לבחירה🤍",
                    features: [
                        "?",
                        "?",
                    ],
                    price: " 50 ₪",
                    link: "https://Oo6Hi48y.web.arboxapp.com/group?whitelabel=Arbox&amp;lang=he&amp;location=17949&amp;referrer=PLUGIN&amp;filters=%7B%22trial%22%3A%22trial%22%2C%22pageName%22%3A%22group%22%7D"
                },
                {
                    id: "guided",
                    class: "guided",
                    title: "🌿 כרטיסיית היכרות 3 כניסות",
                    description: "להכיר את הסטודיו באמת, לנסות אימונים שונים, מאמנות שונות ולהרגיש את האווירה.",
                    features: [
                        "ללא התחייבות",
                        "תקף ל־3 שבועות מרגע הרכישה.",
                        "גישה מלאה לכל השיעורים  באפליקציה",
                    ],
                    price: "99 ₪",
                    link:"https://arbox.link/7cTV8DqR"
                },
                {
                    id: "premium",
                    class: "premium",
                    title: "🌿 חודש היכרות 8 כניסות",
                    description: `להיכנס לשגרה ולבדוק איך הסטודיו משתלב ביום־יום שלך.
                    חודש נותן תמונה אמיתית של תהליך והתמדה 🤍
                    `,
                    features: [
                        "ללא התחייבות ",
                        "תקף ל־30 יום",
                        "גישה מלאה לכל השיעורים באפליקציה",
                    ],
                    price: "349 ₪",
                    link:"https://arbox.link/P8n-N-jO"
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