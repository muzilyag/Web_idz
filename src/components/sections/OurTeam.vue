<template>
    <div class="advisior-section">
        <SectionWithCards
        :members=teamMembers
        :sectionName=thisSectionName
        :grad-text=gradText
        />
    </div>
</template>

<script setup lang="ts">
import SectionWithCards from '../ui/SectionWithCards.vue';

const thisSectionName: string = "Our";
const gradText: string = "Team";

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