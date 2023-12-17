<template>
    <div
        class="problem-card"
        :class="{ 'police-lights': isHovered }"
        @mouseover="isHovered = true"
        @mouseout="isHovered = false"
    >
        <i :class="iconClass"></i>
        <div class="problem-info">
            <h3>{{ title }}</h3>
            <p>{{ description }}</p>
        </div>
    </div>
</template>

<script>
import { ref } from 'vue';
export default {
    props: {
        iconClass: String,
        title: String,
        description: String,
    },
    setup() {
        const isHovered = ref(false);
        return {
            isHovered,
        };
    },
};
</script>

<style scoped>
.problem-card {
    position: relative;
    background-color: #ffffff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    text-align: left;
    overflow: hidden;
    color: #333;
    transition: transform 0.4s ease-in-out;
}

.police-lights {
    animation: police-lights 1.5s infinite linear;
}

@keyframes police-lights {
    0% {
        box-shadow: 0 20px 40px rgba(255, 0, 0, 0.8);
    }
    50% {
        box-shadow: 0 20px 40px rgba(0, 0, 255, 0.8);
    }
    100% {
        box-shadow: 0 20px 40px rgba(255, 0, 0, 0.8);
    }
}

.problem-card:hover {
    transform: scale(1.1);
}

.problem-card i {
    color: #333;
}

.problem-info h3 {
    margin-bottom: 10px;
}

.problem-info p {
    margin: 0;
}
</style>
