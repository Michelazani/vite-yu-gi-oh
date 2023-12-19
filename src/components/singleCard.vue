<script>
export default {
    props: {
        card: {
            type: Object,
            required: true
        }
    }
}
</script>

<template >
    <article class="card">
        <section class="image">
            <img :src="card.card_images[0].image_url" alt="">
        </section>
        <h6 class="text-white text-uppercase">{{ card.name }}</h6>
        <p> {{ card.archetype }}</p>
    </article>
</template> 

<style lang="scss" scoped>
 @use '../style/partials/variables' as *; 

    article.card{
        background-color: $bg-brown;
        text-align: center;
        width: calc((100% / 5) - 1rem);
        margin-left: 0.5rem;
        margin-right: 0.5rem;
        margin-bottom: 0.5rem;
        img{
            width: 100%;
        }
    }
</style>