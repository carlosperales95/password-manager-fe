<template>
    <base-section header="The Password Predicament">
        <div class="cards-container">
            <problem-card
                iconClass="fas fa-lock"
                title="Security Concerns"
                description="More than 80% of breaches happen because of weak or stolen passwords."
                :width="100"
                :height="100"
            ></problem-card>

            <problem-card
                iconClass="fas fa-recycle"
                title="Password Recycling"
                description="An astonishing 90% of us confess to recycling passwords across multiple accounts."
                :width="150"
                :height="150"
            ></problem-card>

            <problem-card
                iconClass="fas fa-shield-alt"
                title="Data Breach Exposure"
                description="Billions of login credentials are exposed yearly in data breaches, leaving us exposed to the shadows of identity theft and unauthorized access."
                :width="120"
                :height="120"
            ></problem-card>

            <problem-card
                iconClass="fas fa-user-secret"
                title="Cyber Attacks"
                description="Every year, an astonishing 8 out of 10 individuals fall victim to at least one successful password hack or cyber attack."
                :width="130"
                :height="130"
            ></problem-card>
            <problem-card
                iconClass="fas fa-ban"
                title="Password Blacklisting"
                description="Using commonly known and easily guessable passwords puts your accounts at risk, as cybercriminals exploit password blacklists."
                :width="120"
                :height="120"
            ></problem-card>

            <problem-card
                iconClass="fas fa-clock"
                title="Password Aging Policies"
                description="Forcing frequent password changes can lead to weaker passwords, as users may resort to predictable patterns or write them down."
                :width="130"
                :height="130"
            ></problem-card>

            <problem-card
                iconClass="fas fa-sync"
                title="Password Synchronization Challenges"
                description="Managing passwords across multiple devices and platforms can be complex, leading to synchronization issues and security gaps."
                :width="140"
                :height="140"
            ></problem-card>

            <problem-card
                iconClass="fas fa-shield-alt"
                title="Inadequate Two-Factor Authentication"
                description="Weak or absent two-factor authentication leaves accounts vulnerable, relying solely on passwords for protection."
                :width="130"
                :height="130"
            ></problem-card>
        </div>
    </base-section>
</template>

<script>
import BaseSection from '../base/BaseSection.vue';
import ProblemCard from '../base/ProblemCard.vue';

export default {
    components: {
        BaseSection,
        ProblemCard,
    },
};
</script>

<style scoped>
.cards-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
    margin-top: 5rem;
}

.cards-container .problem-card {
    flex-grow: 1;
    flex-basis: 0;
    max-width: 100%;
}
</style>
