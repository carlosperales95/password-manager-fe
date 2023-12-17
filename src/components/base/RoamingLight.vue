<template>
    <div class="circle-wrapper" :id="circleId">
        <div
            :class="circleClass"
            :style="{ backgroundColor: circleColor, width: circleSize, height: circleSize }"
        ></div>
    </div>
</template>

<script>
import { computed } from 'vue';

export default {
    props: {
        circleId: String,
        circleColor: String,
        circleSize: String,
        isSmall: Boolean,
    },
    setup(props) {
        const animationDuration = '10s';
        const animationType = 'linear';

        const circleClass = computed(() => {
        return props.isSmall ? 'circle small' : 'circle';
        });

        return { animationDuration, animationType, circleClass };
    },
};
</script>

<style scoped>
.circle-wrapper {
    position: absolute;
    animation: moveCircle var(--animation-duration) var(--animation-type) infinite alternate;
}

.circle {
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background-color: rgba(255, 69, 0, 0.5);
    filter: blur(80px);
    transition: background-color 3s ease-in-out;
}

.small {
    width: 50%;
    height: 50%;
}

@keyframes moveCircle {
    0% {
        transform: translate(-100%, 0);
    }
    30% {
        transform: translate(-40%, -20%);
    }
    70% {
        transform: translate(0, -40%);
    }
    100% {
        transform: translate(40%, -80%);
    }
}

@keyframes moveCircleSmall {
    0% {
        transform: translate(0, 100%);
    }
    30% {
        transform: translate(20%, 40%);
    }
    70% {
        transform: translate(40%, 0);
    }
    100% {
        transform: translate(80%, -40%);
    }
}
</style>
