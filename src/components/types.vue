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
        <div class="types-container" v-if="typesOpen">
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
</script>