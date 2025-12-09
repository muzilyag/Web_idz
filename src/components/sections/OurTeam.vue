<template>
    <div class="team-section">
        <div class="team-section__container">
             <h1 class="section-header">
                Our <span class="gradient-text">Team</span>
            </h1>
            <div class="cards-list">
                <i class="fa-solid fa-chevron-left"></i>
                <div class="cards">
                    <Card
                    v-for="member in teamMembers"
                    :key="member.id"
                    />
                </div>
                <i class="fa-solid fa-chevron-right"></i>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import Card from '../ui/Card.vue';

const teamMembers = [
    {
        id: 1
    },
    {
        id: 2
    },
    {
        id: 3
    }
]
</script>

<style scoped>
.team-section {
    padding: 183px 120px 0 120px;
}

.team-section__container {
    display: grid;
    grid-template-rows: auto auto;
}

.cards-list {
    display: flex;
    gap: 57px;
}

.cards {
    display: grid;
    grid-template-columns: repeat(3, auto);
    gap: 50px;
}

</style>