<template>
  <base-section header="The Password Predicament">
    <div class="background-circles">
      <roaming-light
        v-for="(circle, index) in circles"
        :key="index"
        :circle-id="`circle${index + 1}`"
        :circle-color="circle.color"
        :circle-size="circle.size"
        :is-small="circle.isSmall"
      ></roaming-light>
    </div>
    <div class="cards-container">
      <problem-card
        iconClass="fas fa-lock"
        title="Fortify Now"
        description="Over 80% of breaches occur due to frail or pilfered passwords. Strengthen your digital fortress now."
        :width="1"
      ></problem-card>

      <problem-card
        iconClass="fas fa-recycle"
        title="Break the Cycle"
        description="A staggering 90% of users admit to recycling passwords across various accounts. Break free from the repetition cycle!"
        :width="1"
      ></problem-card>

      <problem-card
        iconClass="fas fa-shield-alt"
        title="Guard Your Data"
        description="Billions of login credentials are exposed yearly in data breaches, exposing us to the shadows of identity theft and unauthorized access."
        :width="2"
      ></problem-card>

      <problem-card
        iconClass="fas fa-user-secret"
        title="Secure Against Attacks"
        description="Every year, 8 out of 10 individuals fall victim to at least one successful password hack or cyber attack. Bolster your defenses!"
        :width="1"
      ></problem-card>

      <problem-card
        iconClass="fas fa-ban"
        title="Avoid Blacklists"
        description="Using commonly known and easily guessable passwords puts your accounts at risk, as cybercriminals exploit password blacklists."
        :width="1"
      ></problem-card>

      <problem-card
        iconClass="fas fa-clock"
        title="Avoid Aging Trap"
        description="Frequent password changes can lead to weaker passwords, as users may resort to predictable patterns or write them down. Avoid the aging trap!"
        :width="2"
      ></problem-card>

      <problem-card
        iconClass="fas fa-sync"
        title="Sync Chaos"
        description="Managing passwords across multiple devices and platforms can be complex, leading to synchronization issues and security gaps."
        :width="1"
      ></problem-card>

      <problem-card
        iconClass="fas fa-shield-alt"
        title="Bridge Security Gap"
        description="Weak or absent two-factor authentication leaves accounts vulnerable, relying solely on passwords for protection. Bridge the security gap!"
        :width="1"
      ></problem-card>
    </div>
  </base-section>
</template>

<script>
import { ref, onMounted } from 'vue';
import BaseSection from '../base/BaseSection.vue';
import ProblemCard from '../base/ProblemCard.vue';
import RoamingLight from '../base/RoamingLight.vue';

export default {
  components: {
    BaseSection,
    ProblemCard,
    RoamingLight,
  },
  setup() {
    const circles = ref([
      { color: getRandomColor(), size: '500px', isSmall: false },
      { color: getRandomColor(), size: '500px', isSmall: false },
      { color: getRandomColor(), size: '250px', isSmall: true },
      { color: getRandomColor(), size: '250px', isSmall: true },
      { color: getRandomColor(), size: '250px', isSmall: true },
    ]);

    const updateColors = () => {
      circles.value.forEach((circle) => {
        circle.color = getRandomColor();
      });
    };

    onMounted(() => {
      // Change colors every 3 seconds
      setInterval(updateColors, 3000);
    });

    return { circles };
  },
};

function getRandomColor() {
  const colors = ['#ff4081', '#ff8c00', '#00bcd4', '#8bc34a', '#ffeb3b'];
  return colors[Math.floor(Math.random() * colors.length)];
}
</script>

<style scoped>
.cards-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 30px;
  margin-top: 2rem;
  padding: 3rem;
  width: 50%;
  margin-left: 50%;
  position: relative;
}

.background-circles {
  position: absolute;
  top: -4rem;
  left: 0;
  width: 100%;
  height: 120%;
  overflow: hidden;
  mask-image: linear-gradient(transparent 8rem, black 10rem, black calc(100% - 10rem), transparent calc(100% - 8rem));
}


#circle2 {
  top: 70%;
  left: 70%;
  animation: moveCircle 10s linear infinite alternate;
}

#circle3 {
  width: 250px;
  height: 250px;
  top: 70%;
  left: 0;
  animation: moveCircleSmall 10s linear infinite alternate;
}

#circle4 {
  width: 250px;
  height: 250px;
  top: 30%;
  left: 30%;
  animation: moveCircleSmall 10s linear infinite alternate;
}

#circle5 {
  width: 250px;
  height: 250px;
  top: 20%;
  left: 80%;
  animation: moveCircleSmall 10s linear infinite alternate;
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
