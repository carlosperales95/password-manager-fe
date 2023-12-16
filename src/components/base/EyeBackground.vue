<template>
    <div class="eye-section">
            <following-eye
                v-for="eye in numberOfEyes"
                :key="eye"
                :cursor-x="cursorX"
                :cursor-y="cursorY"
            ></following-eye>
        </div>
</template>

<script>
import FollowingEye from './FollowingEye.vue';

export default {
    components: {
        FollowingEye,
    },
    props: ['cursorX', 'cursorY', 'numberOfEyes']
}
</script>