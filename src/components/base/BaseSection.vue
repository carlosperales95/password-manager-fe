<template>
    <div class="generic-section">
        <div v-if="header" :class="headerStyle" class="header-container">
            <div class="brushstroke-square">
                <h2 class="brushstroke-text">{{ header }}</h2>
            </div>
        </div>
        <div class="section-content">
            <slot></slot>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        header: String,
        headerStyle: {
            type: String,
            default: 'secondary',
            validator: (value) => ['primary', 'secondary'].includes(value),
        },
    },
};
</script>

<style scoped>
.generic-section {
    margin-bottom: 40px;
    position: relative;
    min-height: 400px;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.header-container {
    display: flex;
    justify-content: center;
}

.brushstroke-square {
    background: rgba(255, 215, 0, 0);
    border: 2px solid;
    border-image: linear-gradient(to right, #ffd700, #ff7f50);
    border-image-slice: 1;
    border-radius: 10px;
    padding: 10px;
    width: 50%;
    text-align: center;
}

.secondary .brushstroke-text {
    font-size: 1.8em;
    margin: 0;
    background: linear-gradient(to right, #ffd700, #ff7f50);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    display: inline-block;
}

.primary .brushstroke-text {
    font-size: 1.8em;
    margin: 0;
    color: rgb(10, 14, 11);
    background: linear-gradient(to right, #ffd700, #ff7f50);
}
</style>
