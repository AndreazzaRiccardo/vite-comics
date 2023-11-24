<script>
export default {
    props: {
        title: String,
        imgTitle: String,
    }
}
</script>

<template>
    <div class="card">
        <img :src="imgTitle" :alt="title">
        <h3>{{ title }}</h3>
    </div>
</template>

<style scoped lang="scss">

    .card {
        margin-top: 1rem;
        img {
            width: 100%;
            aspect-ratio: 1;
            object-fit: cover;
            object-position: top;
        }

        h3 {
        height: 30px;
        margin-top: 1rem;
        color: white;
    }
    }
    
</style>