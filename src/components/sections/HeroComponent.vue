<template>
    <div class="hero-container">
        <div class="hero">
            <h1 v-if="hasTitle">{{ heroTitle }}</h1>
            <p v-if="hasDescription">{{ heroDesc }}</p>
            <button v-if="hasAction" @click="performAction">{{ heroAction }}</button>
        </div>
        <video width="320" height="240" autoplay loop muted>
            <source src="../../assets/burning-house.mp4" type="video/mp4" />
            Your browser does not support the video tag.
        </video>

    </div>
</template>

<script>
import { computed } from 'vue';

export default {
    props: ['title', 'description', 'action'],
    setup(props) {
        console.log(props.title);
        
        const hasTitle = computed(function() {
            return props.title !== '';
        });

        const hasDescription = computed(function() {
            return props.description !== '';
        });

        const hasAction = computed(function() {
            return props.action !== '';
        });

        const performAction = function() {
            console.log("Clicked");
        }

        return {
            heroTitle: props.title,
            hasTitle,
            heroDesc: props.description,
            hasDescription,
            heroAction: props.action,
            hasAction,
            performAction
        };
    },
}
</script>

<style scoped>
h1 {
    font-size: 55px;
    margin-bottom: 0;
}

p {
    font-size: 22px;
}

.hero-container {
    padding: 0;
    margin: 0;
    height: 22rem;
    overflow: hidden;
    text-align: center;
    align-content: center;
    margin-bottom: 19rem;
}

.hero {
    position: absolute;
    z-index: 1;
    height: 15rem;
    width: inherit;
    left: 0;
    right: 0;
    margin: 2rem;
    margin-left: 25%;
    margin-right: 25%;
    padding: 1rem;
    text-align: center;
    background-color: rgba(10, 14, 11, 0.8);
    border-bottom: 2px solid #ccc;
    border-radius: 1rem;
}

video {
    width: 100%;
    top: -150px;
    min-width: auto;
    max-height: 150%;
    width: auto;
    height: auto;
    z-index: -100;
    background-size: cover;
}

button {
    color: inherit;
    padding: 0.3rem;
    font-size: 18px;
    font-weight: 700;
    width: 8rem;
    height: 2.5rem;
    text-transform: uppercase;
    background-color: rgb(15, 184, 113);
    border: 2px solid #ccc;
    border-radius: 0.4rem;
}

button:hover {
    background-color: rgb(19, 223, 138);
    border: 2px solid rgb(10, 14, 11);
    color: rgb(10, 14, 11);
    cursor: pointer;
}

</style>