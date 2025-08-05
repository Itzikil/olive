<template>
    <!-- <section class="contact-form"> -->
    <section id="contactForm" class="contact-form">
        <h2>השאירו פרטים ונחזור אליכם</h2>
        <form @submit.prevent="submitForm">
            <input type="text" v-model="form.name" placeholder="שם מלא" required />
            <input type="tel" v-model="form.phone" placeholder="מספר טלפון" required />
            <textarea v-model="form.message" placeholder="הודעה (לא חובה)"></textarea>
            <button type="submit">שלח</button>
        </form>
    </section>
</template>

<script>
export default {
    data() {
        return {
            form: {
                name: '',
                phone: '',
                message: ''
            }
        };
    },
    methods: {
        submitForm() {
            // Handle form logic here (send to server, validation, etc.)
            alert(`תודה ${this.form.name}, נחזור אליך בהקדם!`);
            this.form = { name: '', phone: '', message: '' };
        }
    }
};
</script>
