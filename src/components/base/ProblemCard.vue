<template>
  <div
    :class="['problem-card', styleClass]"
    :style="{ gridColumn: `span ${width}` }"
    @mouseover="isHovered = true"
    @mouseout="isHovered = false"
  >
    <i :class="iconClass"></i>
    <div class="problem-info">
      <h3 class="card-title">{{ title }}</h3>
      <p class="card-description">{{ description }}</p>
    </div>
  </div>
</template>

<script>
import { ref, computed } from 'vue';

export default {
  props: {
    iconClass: String,
    title: String,
    description: String,
    width: {
      type: Number,
      default: 1,
    },
    primary: {
      type: Boolean,
      default: false,
    },
  },
  setup(props) {
    const isHovered = ref(false);
    const styleClass = computed(() => (props.primary ? 'primary' : 'secondary'));

    return {
      isHovered,
      styleClass,
    };
  },
};
</script>

<style scoped>
.problem-card {
  position: relative;
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: left;
  overflow: hidden;
  color: #fff;
  transition: transform 0.4s ease-in-out, box-shadow 0.5s ease-in-out;
  font-size: 18px;
}

.problem-card i {
  font-size: 2em;
  margin-right: 10px;
  transition: color 0.4s ease-in-out;
}

.problem-info h3 {
  margin-bottom: 10px;
}

.problem-info p {
  margin: 0;
}

.problem-card:hover {
  transform: scale(1.1);
  animation: police-lights 1.5s infinite linear;
}

@keyframes police-lights {
  0%, 100% {
    box-shadow: 0 20px 40px rgba(0, 0, 255, 0.8);
  }
  50% {
    box-shadow: 0 20px 40px rgba(255, 0, 0, 0.8);
  }
}

.problem-card.primary {
  background-color: rgba(50, 50, 50, 0.5);
  border-radius: 15px;
}

.problem-card.primary:hover h3,
.problem-card.primary:hover i {
  color: rgb(10, 14, 11);
}

.problem-card.primary:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  border: 2px solid transparent;
  border-radius: 15px;
  background: linear-gradient(to right, #ff4081, #ff8c00);
  z-index: -1;
}

.problem-card.secondary {
  background-color: rgba(50, 50, 50, 0.171);
  border: 2px solid;
  border-image: linear-gradient(to right, #ff4081, #ff8c00);
  border-image-slice: 1;
}

.problem-card.secondary i {
  color: #ff4081;
}

.card-title {
  font-size: 1.5em;
  background: linear-gradient(to right, #ff4081, #ff8c00);
  -webkit-background-clip: text;
  color: transparent;
  margin-bottom: 10px;
}

.card-description {
  margin: 0;
  font-size: 1em;
}
</style>
