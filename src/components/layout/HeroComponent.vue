<template>
    <div class="hero">
        <h1>{{ heroTitle }}</h1>
        <p>{{ heroDesc }}</p>
        <button>{{ heroAction }}</button>
    </div>
</template>

<script>
export default {
    props: ['title', 'description', 'action'],
    setup(props) {
        console.log(props.title);

        return {
            heroTitle: props.title,
            heroDesc: props.description,
            heroAction: props.action
        };
    },
}
</script>

<style scoped>

.hero {
    margin: 1rem auto;
    border: 1px solid #ccc;
    border-radius: 12px;
    padding: 1rem;
    text-align: center;
}

</style>