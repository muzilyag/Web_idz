<template>
    <div class="section">
        <div class="section__container">
             <h1 class="section__header">
                {{ sectionName }} <span class="gradient-text">{{gradText}}</span>
            </h1>
            <div class="cards-list">
                <i class="fa-solid fa-chevron-left"></i>
                <div class="cards">
                    <Card
                    v-for="member in members"
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

interface Props {
    sectionName?: string;
    gradText?: string;
    members: Array<{id: number}>;
}

const props = withDefaults(defineProps<Props>(), {})
</script>

<style scoped>
.section {
    padding: 150px 120px 0 120px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.section__header {
    display: flex;
    justify-content: center;
    gap: 12px;
}

.section__container {
    display: grid;
    grid-template-rows: auto auto;
    gap: 80px;
}

.cards-list {
    display: flex;
    gap: 57px;
    align-items: center;
}

.cards {
    display: grid;
    grid-template-columns: repeat(3, auto);
    gap: 50px;
}

.gradient-text {
    background: linear-gradient(90deg, #3AC4FF 0, #AE61ED 80%);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    color: transparent;
}

.cards-list .fa-solid {
    cursor: pointer;
    scale:1.9;
}

.cards-list .fa-solid:hover {
    scale: 2.9;
    transition: all ease 0.6s;
}

</style>