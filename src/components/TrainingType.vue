<!-- TrainingType.vue -->
<template>
    <div class="training-type" :class="{ open: isOpen }">
        <button class="training-header" @click="$emit('toggle')">
            <div class="title-wrapper">
                <!-- <img v-if="icon" src="../assets/imgs/pilates.svg" :alt="title"> -->
                <h2>{{ title }}</h2>
            </div>

            <span class="arrow" :class="{ rotate: isOpen }">
                +
            </span>
        </button>

        <Transition name="expand">
            <div v-if="isOpen" class="details">
                <p v-html="formattedDescription"></p>
            </div>
        </Transition>
    </div>
</template>


<script>
export default {
    name: 'TrainingType',
    props: {
        title: String,
        description: String,
        isOpen: Boolean
    },

    computed: {
        formattedDescription() {
            return this.description.replace(/\n/g, '<br>')
        }
    },

    methods: {
        toggleDetails() {
            // this.isOpen = !this.isOpen

            this.$emit('toggle', this.title)
        }
    }
}
</script>

<style scoped lang="scss">
.training-type {
    background-color: #fff;
    border-radius: 24px;
    padding: 1rem 1.2rem;
    // box-shadow: 0 4px 18px rgba(0, 0, 0, 0.06);
    transition: 0.3s ease;
    overflow: hidden;

    &.open {
        // box-shadow: 0 8px 28px rgba(0, 0, 0, 0.1);
    }
}

.training-header {
    width: 100%;
    // border: none;
    background: white;
    // display: flex;
    // align-items: center;
    justify-content: space-between;
    cursor: pointer;
    padding: 0;
    box-shadow: none;
}

.title-wrapper {
    display: flex;
    align-items: center;
    gap: 0.8rem;
    box-shadow: none;

    img {
        width: 34px;
        height: 34px;
        object-fit: contain;
    }

    h2 {
        margin: 0;
        font-size: 1.2rem;
        font-weight: 700;
        color: #222;
        text-align: right;
    }
}

.arrow {
    font-size: 1.8rem;
    font-weight: 300;
    transition: transform 0.3s ease;

    &.rotate {
        transform: rotate(45deg);
    }
}

.details {
    padding-top: 1rem;

    p {
        margin: 0;
        line-height: 1.8;
        color: #555;
        font-size: 0.98rem;
        white-space: normal;
    }
}

/* animation */
.expand-enter-active,
.expand-leave-active {
    transition: all 0.35s ease;
    overflow: hidden;
}

.expand-enter-from,
.expand-leave-to {
    max-height: 0;
    opacity: 0;
    transform: translateY(-6px);
}

.expand-enter-to,
.expand-leave-from {
    max-height: 500px;
    opacity: 1;
    transform: translateY(0);
}
</style>