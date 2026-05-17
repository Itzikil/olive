<template>
    <section class="reviews-section">

        <div class="reviews-header">
            <p class="small-title">{{ smallTitle }}</p>

            <h2>{{ title }}</h2>

            <a :href="googleLink" target="_blank" rel="noopener noreferrer" class="google-btn">
                ⭐ לכל הביקורות
            </a>
        </div>

        <div class="reviews-grid">

            <article v-for="review in reviews" :key="review.name" class="review-card">
                <div class="review-top">

                    <div>
                        <h3>{{ review.name }}</h3>

                        <span>
                            {{ '★'.repeat(review.rating) }}
                        </span>
                    </div>

                    <div class="google-icon">
                        G
                    </div>

                </div>

                <p>
                    {{ review.text }}
                </p>
            </article>

        </div>

    </section>
</template>

<script>
export default {
    name: 'GoogleReviews',

    props: {
        smallTitle: {
            type: String,
            default: 'לקוחות ממליצים'
        },

        title: {
            type: String,
            default: 'מה אומרים עלינו בגוגל'
        },

        // googleLink: {
        //     type: String,
        //     required: true
        // },

        // reviews: {
        //     type: Array,
        //     default: () => []
        // }
    },
    data() {
        return {
            googleLink: "https://share.google/D3lKNqM55qO5gKIaU",
            reviews: [
                {
                    name: 'ישראל כהן',
                    rating: 5,
                    text: 'שירות מדהים, מקצועי ואדיב מאוד.'
                },

                {
                    name: 'נועה לוי',
                    rating: 5,
                    text: 'חוויה מעולה, ממליצה בחום.'
                },

                {
                    name: 'אור בן דוד',
                    rating: 5,
                    text: 'איכות גבוהה ויחס אישי מההתחלה ועד הסוף.'
                }
            ]
        };
    },
}
</script>

<style>
.reviews-section {
    padding: 5rem 1.5rem;
    background: #f7f7f7;
    border-radius: 10px;

    .reviews-header {
        text-align: center;
        margin-bottom: 3rem;

        .small-title {
            color: #777;
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
        }

        h2 {
            font-size: clamp(2rem, 5vw, 3rem);
            margin-bottom: 1.5rem;
            color: #111;
        }

        .google-btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;

            padding: 0.9rem 1.5rem;
            border-radius: 999px;

            background: #fff;
            color: #111;

            text-decoration: none;
            font-weight: 600;

            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.06);

            transition: 0.25s ease;

            &:hover {
                transform: translateY(-3px);
                box-shadow: 0 12px 30px rgba(0, 0, 0, 0.1);
            }
        }
    }

    .reviews-grid {
        display: flex;
        flex-wrap: wrap;
        /* grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); */
        gap: 1.5rem;

        max-width: 1200px;
        margin: auto;
    }

    .review-card {
        background: #fff;

        padding: 1.5rem;

        border-radius: 24px;

        box-shadow: 0 10px 35px rgba(0, 0, 0, 0.05);

        transition: 0.3s ease;

        display: flex;
        flex-direction: column;
        gap: 1.2rem;

        &:hover {
            transform: translateY(-6px);
        }

        .review-top {
            display: flex;
            align-items: center;
            justify-content: space-between;

            h3 {
                margin: 0;
                font-size: 1rem;
                color: #111;
            }

            span {
                color: #f4b400;
                font-size: 0.95rem;
            }

            .google-icon {
                width: 42px;
                height: 42px;

                border-radius: 50%;

                background: #f1f1f1;

                display: flex;
                align-items: center;
                justify-content: center;

                font-weight: 700;
                color: #4285F4;
            }
        }

        p {
            margin: 0;
            line-height: 1.7;
            color: #444;
            font-size: 1rem;
        }
    }
}
</style>