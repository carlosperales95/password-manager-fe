<template>
    <div class="custom-section" :style="{ background: backgroundColor, color: textColor }">
        <div class="container">
            <h2>{{ sectionTitle }}</h2>
            <p>{{ sectionContent }}</p>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        backgroundColor: {
            type: String,
            required: true,
        },
        textColor: {
            type: String,
            required: true,
        },
        sectionTitle: {
            type: String,
            required: true,
        },
        sectionContent: {
            type: String,
            required: true,
        },
    },
};
</script>

<style scoped>
.custom-section {
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.container {
    max-width: 800px;
    margin: 0 auto;
    padding: 40px;
    text-align: center;
}

h2 {
    font-size: 2em;
    margin-bottom: 10px;
}

p {
    font-size: 1.2em;
}
</style>
