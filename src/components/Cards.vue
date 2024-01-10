<script>
export default {
    props: {
        card: Object,
    },
    data() {
        return {

        }
    }
}
</script>
<template lang="">
    <div class="card">
        <img :src="card.card_images[0].image_url" >
        <div>
            <p class="text color-w">{{ card.name }}</p>
            <p class="text">{{ card.archetype }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card {
    width: calc(100% / 5 - 40px);
    padding: 10px;
    background-color: rgb(165, 122, 42);
    margin: 10px;


    img {
        width: 100%;
    }

    .text {
        font-weight: bold;
        font-family: Verdana, Geneva, Tahoma, sans-serif;
        font-size: 12px;
        text-align: center;
    }

    .color-w {
        color: white;
    }
}
</style>