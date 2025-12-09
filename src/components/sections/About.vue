<template>
    <div class="about">
        <div class="about__container">
            <h1 class="section__header">About Us</h1>
            <p class="section__content">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
                sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi 
                ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit 
                in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                Excepteur sint occaecat cupidatat non proident, sunt in culpa qui 
                officia deserunt mollit anim id est laborum.
            </p>
            <div class="about__actions">
                <button class="about__button about__button-content">
                    Try Web3ATL Now
                </button>
                <button class="about__button about__button-content">
                    Try Web3ATL Now
                </button>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts"></script>

<style scoped>

.about {
    padding: 140px 80px 0 140px;
}

.about__container {
    display: grid;
    grid-template-rows: repeat(auto, 3);
    gap: 30px;
}

.about__actions {
    display: flex; 
    gap: 15px;
}

.about__button {
    padding: 11px 24px;
    border-radius: 8px;
    background-image: linear-gradient(to right, #1F8EBE, #AE61ED);
    border: none;
    box-shadow: 0 17px 33px #FFFFFF33;
}

.about__button-content {
    font-size: 0.875rem;
    line-height: 140%;
    font-weight: 600;
    color: var(--main-text);
}

.about__button:hover {
    scale: 1.1;
    transition: all 0.7s ease;
}

</style>