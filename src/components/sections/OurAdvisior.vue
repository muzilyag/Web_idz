<template>
    <div class="advisior-section">
        <SectionWithCards
        :members=advMembers
        :sectionName=thisSectionName
        :grad-text=thisGradText
        />
    </div>
</template>

<script setup lang="ts">
import SectionWithCards from '../ui/SectionWithCards.vue';

const thisSectionName: string = "Our";
const thisGradText: string = "Advisor";
const advMembers = [
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