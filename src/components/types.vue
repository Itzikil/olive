<template>
    <section id="types" class="types">
        <h3>סוגי אימונים</h3>
        <p>כאן משלבים פילאטיס מכשירים ואימוני כוח מגוונים,
            באווירה משפחתית, מדויקת ומקצועית,
            כזו שמחזיקה לאורך זמן, ולא רק לאימון אחד, מתאים לכל הרמות.</p>

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