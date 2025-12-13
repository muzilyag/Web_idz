<template>
    <div class="text-block">
        <div class="text-block__container">
            <div 
                v-for="(block, index) in textBlocks" 
                :key="index" 
                class="text-block__section"
            >
                <h1 class="section__header">{{ block.header }}</h1>
                <div class="section__content">
                    <p v-for="(paragraph, pIndex) in block.paragraphs" :key="pIndex">
                        {{ paragraph }}
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';

interface TextBlock {
    header: string;
    paragraphs: string[];
}

const textBlocks = ref<TextBlock[]>([]);

async function loadTextFromFile() {
    try {
        const response: Response = await fetch('/text-data.txt');
        const fileContent: string = await response.text();
        
        const blocks: TextBlock[] = [];
        
        const sectionRegex: RegExp = /\[([^\]]+)\]\s*([^[]*)/g;
        let match: RegExpExecArray | null;
        
        while ((match = sectionRegex.exec(fileContent)) !== null) {
            if (match[1] && match[2]) {
                const header: string = match[1].trim();
                const content: string = match[2].trim();
                
                const paragraphs: string[] = content
                    .split('\n')
                    .map(line => line.trim())
                    .filter(line => line.length > 0);
                
                if (paragraphs.length > 0) {
                    blocks.push({
                        header: header,
                        paragraphs: paragraphs
                    });
                }
            }
        }
        
        if (blocks.length > 0) {
            textBlocks.value = blocks;
            console.log('Загружено блоков:', blocks.length);
        }
        
    } catch (error) {
        console.log('Ошибка загрузки файла');
    }
}

onMounted(() => {
    loadTextFromFile();
});

function reloadText() {
    loadTextFromFile();
}

defineExpose({ reloadText });
</script>

<style scoped>

.text-block {
    padding: 140px 80px 0 140px;
}

.text-block__container {
    display: grid;
    grid-template-rows: repeat(auto, 3);
    gap: 80px;
}

.text-block__section {
    display: grid;
    grid-template-rows: auto auto;
    gap: 30px;
}

</style>