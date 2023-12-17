<template>
    <div class="feature-section">
        <div class="cards-container-group">
            <div class="cards-container">
                <base-card cardBackgroundColor="#3498db" textColor="#ffffff">
                    <i class="fas fa-magic icon"></i>
                    <div class="feature-info">
                    <h2>Password Alchemist</h2>
                    <p>Unleash the power of our password generator, crafting intricate codes to fortify your digital fortress against intruders.</p>
                    </div>
                </base-card>

                <base-card cardBackgroundColor="#e74c3c" textColor="#ffffff">
                    <i class="fas fa-eye icon"></i>
                    <div class="feature-info">
                    <h2>Breach Guardian</h2>
                    <p>Stand vigilant with our real-time breach monitoring, alerting you instantly if your digital identity is ever compromised.</p>
                    </div>
                </base-card>

                <base-card cardBackgroundColor="#2ecc71" textColor="#ffffff">
                    <i class="fas fa-shield-alt icon"></i>
                    <div class="feature-info">
                    <h2>Vault Sentinel</h2>
                    <p>Enlist the secure vault encryption, your digital fortress guarded by military-grade encryption for unparalleled data security.</p>
                    </div>
                </base-card>

                <base-card cardBackgroundColor="#9b59b6" textColor="#ffffff">
                    <i class="fas fa-lock icon"></i>
                    <div class="feature-info">
                    <h2>Cryptic Vault</h2>
                    <p>Enter the Cryptic Vault, where your digital treasures are safe under the guardianship of advanced encryption. Rest easy, for your data is shielded from the prying eyes of the digital underworld.</p>
                    </div>
                </base-card>
            </div>
        </div>
    </div>
</template>

<script>
import BaseCard from '../base/BaseCard.vue';

export default {
    components: {
        BaseCard,
    },
};
</script>

<style scoped>
.feature-section {
    background-size: cover;
    background-position: center;
    padding: 50px 0;
    text-align: center;
    background-image: url('../../assets.logo.svg');
}

.cards-container-group {
    width: 50%;
    margin: 0;
}

.cards-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: repeat(2, auto);
    gap: 20px;
    max-width: 1200px;
    margin: 0 auto;
}

.base-card {
    padding: 15px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.icon {
    font-size: 3em;
    margin-bottom: 10px;
}

.feature-info {
    text-align: center;
}

.feature-info h2 {
    margin-bottom: 10px;
    font-size: 1.5em;
}

.feature-info p {
    margin: 0;
    font-size: 1em;
}

</style>
