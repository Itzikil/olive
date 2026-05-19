<template>
    <section id="types" class="types">
        <h2>סוגי אימונים</h2>

        <div class="types-info">
            <p>
                כאן אנחנו משלבות בין עולמות פילאטיס מכשירים ואימוני כוח.
            </p>

            <p>
                תוכלי למצוא אצלנו מגוון אימונים מאתגרים באווירה משפחתית ותומכת —
                כזו שמחזיקה לאורך זמן.
            </p>

            <p>
                צוות המאמנות שלנו דואגות להתאים את האימון בדיוק אלייך,
                כדי לאפשר לכל מתאמנת — בין אם היא מתחילה או מנוסה —
                לקבל אימון מקצועי, מדויק ומאתגר.
            </p>
        </div>

        <div class="types-container">
            <TrainingType v-for="type in trainingTypes" :key="type.title" :title="type.title"
                :description="type.description" :icon="type.icon" />
        </div>
    </section>
</template>

<script>
import TrainingType from './TrainingType.vue'

export default {
    name: 'Types',

    components: {
        TrainingType
    },

    data() {
        return {
            trainingTypes: [
                {
                    title: 'פילאטיס מכשירים',
                    description: `שיעור פילאטיס מכשירים באורך 50 דקות, המתמקד בחיזוק שרירי הליבה, פלג הגוף התחתון, חגורת הכתפיים, גמישות ויציבות.

האימון משלב עבודה על מיטות פילאטיס ייעודיות המסייעות לשיפור יכולת התנועה, השליטה והסיבולת.

מתאים לכל הרמות ומאפשר לכל מתאמנת ליהנות מאימון מותאם אישית לצד אתגרים חדשים.`
                },

                {
                    title: 'Jumping Board',
                    description: `שיעור פילאטיס מכשירים המשלב עבודה עם "קרש קפיצה".

האימון מאפשר לבצע תנועות קפיצה ודחיפה בשכיבה או בזוויות שונות תוך התנגדות של קפיצי המיטה.

השילוב יוצר אימון שמעלה דופק כמו פעילות אירובית, אך נשאר עדין יחסית למפרקים בזכות התמיכה של המכשיר והעבודה ללא עומסים.`
                },

                {
                    title: 'פילאטיס בר',
                    description: `אימון בר עוצמתי לחיזוק וחיטוב הגוף, המשלב עבודה על סיבולת לב־ריאה, גמישות ויציבה.

אימון מדויק, זורם ומלא אנרגיה.

לא מתאים לנשים בטרימסטר הראשון להריון.`
                },

                {
                    title: 'אימון כוח',
                    description: `אימון כוח עם מערך משתנה מאימון לאימון, הנבנה על ידי צוות המאמנות שלנו.

אימון מלא באנרגיה, אתגר ותנועה.

בניית כוח • חיטוב • חיזוק העצמות`
                },

                {
                    title: 'Pure Power',
                    description: `אימון כוח קלאסי עם ציוד מקצועי, בדגש על טכניקה נכונה, זמני מנוחה מסודרים ועלייה הדרגתית במשקלי העבודה.

אימון מדויק שמאפשר התקדמות עקבית לאורך זמן.

בניית כוח • חיטוב • חיזוק העצמות`
                },

                {
                    title: 'Super S',
                    description: `אימון כוח דינמי הבנוי כולו מסופר־סטים בשילוב ציוד מקצועי.

אימון מאתגר בקצב גבוה עם עבודה רציפה ואנרגטית.

בניית כוח • חיטוב • שיפור סיבולת`
                },

                {
                    title: 'PBS',
                    description: `PBS | Power Body Shape

אימון כוח המותאם לנשים ומתמקד בעיצוב וחיטוב הגוף כולו.

30 דקות פלג גוף תחתון בדגש על ישבן.
10–12 דקות פלג גוף עליון בקצב גבוה ומנוחות קצרות.
13–15 דקות בטן וישבן.

אימון מדויק, מחטב ומלא אנרגיה.`
                }
            ]
        }
    }
}
</script>

<style scoped lang="scss">
.types {
    padding: 4rem 1.5rem;
    width: 100%;

    h2 {
        text-align: center;
        font-size: 2.4rem;
        margin-bottom: 1.5rem;
    }
}

.types-info {
    max-width: 850px;
    margin: 0 auto 3rem;
    text-align: center;

    p {
        line-height: 1.9;
        color: #555;
        margin-bottom: 1rem;
        font-size: 1.05rem;
    }
}

.types-container {
    // display: flex;
    // flex: wrap;
    // display: grid;
    // gap: 1rem;
    // max-width: 850px;
    // margin: 0 auto;
}
</style>




<!-- 


<template>
    <section id="types" class="types">
        <h2>סוגי אימונים</h2>
        <div>
            <p>כאן אנחנו משלבות בין עולמות פילאטיס מכשירים ואימוני כוח.</p>
            <p>תוכלי למצוא אצלנו מגוון אימונים מאתגרים באווירה משפחתית ותומכת -
                כזו שמחזיקה לאורך זמן.</p>
            <p>צוות המאמנות שלנו דואגות להתאים את האימון בדיוק אליך כדי לאפשר
                לכל מתאמנת בין אם היא מתחילה או מנוסה לקבל אימון מדוייק מקצועי ומתאגר.</p>
        </div>
        <button @click="typesOpen = !typesOpen">לכל סוגי האימונים</button>
        <div class="types-container">
            <PurePower @type-shown="openType" />
            <SuperS @type-shown="openType" />
            <JumpingBoard @type-shown="openType" />
            <PilatesBar @type-shown="openType" />
        </div>
        
        <div class="show-type" v-if="typeShown">
            {{ typeShown }}
            <button @click="typeShown = null">סגור</button>
        </div>
    </section>
</template>

<script>
import SuperS from "./TrainingTypes/SuperS.vue";
import JumpingBoard from "./TrainingTypes/JumpingBoard.vue";
import PilatesBar from "./TrainingTypes/PilatesBar.vue";
import PurePower from "./TrainingTypes/PurePower.vue";

export default {
    name: "Types",
    data() {
        return {
            typesOpen: false,
            typeShown: null,
        };
    },
    methods: {
        openType(desc) {
            if (this.typeShown === desc) this.typeShown = null
            else this.typeShown = desc;
        }
    },
    components: {
        SuperS,
        JumpingBoard,
        PilatesBar,
        PurePower,
    }
};
</script> -->