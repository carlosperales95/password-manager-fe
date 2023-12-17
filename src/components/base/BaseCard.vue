<template>
    <div class="base-card" :style="{ backgroundColor: cardBackgroundColor, color: textColor }">
        <slot></slot>
    </div>
</template>

<script>
export default {
    props: {
        cardBackgroundColor: String,
        textColor: String,
    },
};
</script>

<style scoped>
.base-card {
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

h2, p {
    margin: 0;
}

h2 {
  font-size: 1.5em; /* Adjusted font size */
}

p {
  font-size: 1em; /* Adjusted font size */
}

/* Add more styling as needed */
</style>
