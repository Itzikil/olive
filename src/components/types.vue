<template>
    <section id="types" class="types">
        <h3>סוגי אימונים</h3>
        <p>כאן משלבים פילאטיס מכשירים ואימוני כוח מגוונים,
            באווירה משפחתית, מדויקת ומקצועית,
            כזו שמחזיקה לאורך זמן, ולא רק לאימון אחד, מתאים לכל הרמות.</p>

        <button @click="typesOpen = !typesOpen">לכל סוגי האימונים</button>
        <div class="types-container" v-if="typesOpen">
            <PurePower />
            <SuperS />
            <JumpingBoard />
            <PilatesBar />
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
            typesOpen: false
        };
    },
    components: {
        SuperS,
        JumpingBoard,
        PilatesBar,
        PurePower,
    }
};
</script>