<template>
    <div class="eye-outer">
        <div class="eye" @mouseenter="closeEye" @mouseleave="openEye" ref="root"></div>
    </div>
</template>

<script>
import { watch, ref } from "vue";

export default {
    props: ['cursorX', 'cursorY'],
    setup(props) {
        const root = ref(null);
        
        const openEye = function(event) {
            // console.log("open eye");
        };

        const closeEye = function(event) {
            // console.log("close eye");
        };


        watch(() => props.cursorX, () => {
            let x = (root.value.getBoundingClientRect().left) + (root.value.clientWidth / 2);
            let y = (root.value.getBoundingClientRect().top) + (root.value.clientHeight / 2);

            let radian = Math.atan2(props.cursorX - x, props.cursorY - y);
            let rotation = (radian * (180 / Math.PI) * -1) + 270;
            
            root.value.style.transform = `rotate(${rotation}deg)`;
        });

        return {
            openEye,
            closeEye,
            root,
        };
    },
}
</script>

<style scoped>
.eye-outer {
    position: relative;
    width: 80px;
    height: 80px;
    background: #fff;
    border-radius: 50%;
    overflow: hidden;
}

.eye {
    width: inherit;
    height: inherit;
    background: inherit;
    border-radius: inherit;
    overflow: inherit;
    box-shadow: 0 5px 45px rgba(0,0,0,0.2),
                inset 0 0 15px #551d1d,
                inset 0 0 15px #f2371e;
}

.eye::before {
    content: '';
    position: absolute;
    top: 50%;
    left: 30px;
    transform: translate(-50%, -50%);
    width: 30px;
    height: 30px;
    border-radius: 50%;
    backdrop-filter: #000;
    border: 10px solid #551d1d;
    box-sizing: border-box;
}

.eye-outer::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 80px;
    height: 4px;
    background-color: #522222;
    transition: height 0.1s ease-out;
    border-bottom: 1px solid #551d1d;
}

.eye-outer:hover::after {
    height: 80px;
}
</style>