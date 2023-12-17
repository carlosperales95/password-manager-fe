<template>
    <div class="eye-text-section">
        <div class="top-hover-text">
            <h2>{{title}}</h2>
        </div>
        <login-card
            class="hover-text"
            :title="'Log into your account'"
        ></login-card>
        <div class="eye-container" @mousemove="followCursor($event)">
            <eye-background
                :numberOfEyes="countEyes"
                :cursor-x="cursorX"
                :cursor-y="cursorY"
            ></eye-background>
        </div>
        <span></span>
    </div>
</template>

<script>
import EyeBackground from '../base/EyeBackground.vue';
import LoginCard from "../base/LoginCard.vue";
import { ref, onMounted, onUnmounted } from "vue";

export default {
    components: {
        EyeBackground,
        LoginCard
    },
    props: ['title', 'infoText'],
    setup() {
        const cursorX = ref(null);
        const cursorY = ref(null);
        const countEyes = ref(0);

        const followCursor = function (event) {
            cursorX.value = event.pageX;
            cursorY.value = event.pageY;
        };

        const calculateEyes = function() {
            const section = document.querySelector('.eye-section');
            const sectionH = section.clientHeight;
            const sectionW = section.clientWidth;

            const sectionColumns = Math.floor(sectionW / 85);
            const sectionRows = Math.floor(sectionH/ 85);
            countEyes.value = sectionColumns * sectionRows;
        };

        onMounted(() => {
            calculateEyes();
            window.addEventListener('resize', calculateEyes)
        });
        
        onUnmounted(() => window.removeEventListener('resize', calculateEyes));

        return {
            followCursor,
            cursorX,
            cursorY,
            countEyes
        };
    },
}
</script>


<style scoped>
@font-face {
    font-family: 'emizen';
    src: url('../../assets/fonts/Emizen.ttf');
}

.eye-text-section {
    text-align: center;
    color: inherit;
    margin-top: 4rem;
}

.eye-container {
    background-color: rgb(82, 16, 11);
    color: rgb(10, 14, 11);
    height: 34rem;
    display: flex;
    background-size: cover;
    border-radius: 40%;
    box-shadow: inset 0rem -1rem 3rem 3rem rgb(10, 14, 11);
}

.top-hover-text {
    box-shadow: 0 1rem 1rem 1rem rgb(10, 14, 11);
    background-color: rgb(10, 14, 11);
    align-self: center;
    position: absolute;
    width: 100%;
    height: 13rem;
    top: inherit;
    margin: 0;
    padding: 1rem;
    z-index: 999;
}

.hover-text {
    background-color: rgb(10, 14, 11);
    align-self: center;
    position: relative;
    width: 30%;
    left: 35%;
    top: 18rem;
    margin: 0;
    z-index: 999;
    padding-top: 2px;
}

.eye-section {
    margin-top: 8rem;
    width: 100%;
    height: 80%;
    display: inline-flex;
    flex-flow: row wrap;
    /* flex: 1 1 0px; */
    justify-content: space-around;
    align-content: flex-start;
}

span {
    display: block;
    position: relative;
    width: 100%;
    height: 1rem;
    box-shadow: 0 -2rem 2rem 4rem rgb(10, 14, 11);
}

h2 {
    font-family: 'emizen';
    font-size: 39px;
    text-transform: uppercase;
    font-style: italic;
}
</style>