<template>
    <section class="schedule-container" id="schedule">
        <button @click="toggleSchedule">
            {{ showSchedule ? 'לסגירת לוח זמנים' : 'לפתיחת לוח זמנים' }}
        </button>
        <iframe v-if="showSchedule"
            src="https://oo6hi48y.web.arboxapp.com/group?whitelabel=Arbox&lang=he&location=17949&referrer=SITE&allLocations=false"
            width="100%" height="800" frameborder="0" loading="lazy">
        </iframe>
        <!-- <img src="../assets/imgs/schedule.png" alt=""> -->
    </section>
</template>

<script>
export default {
    name: "Schedule",
    data() {
        return {
            showSchedule: false
        };
    },
    methods: {
        toggleSchedule() {
            this.showSchedule = !this.showSchedule;
        }
    }
}


</script>