<script lang="ts" setup>

const loadingSubmit = ref(false);

const items = ref([
   "DeepSeek4-flash",
   "DeepSeek4-pro" 
]);
const defaultModel = ref("DeepSeek4-flash");


const handleSubmit = () => {
   loadingSubmit.value = true;
   
};
</script>
<template>
    <div class="w-2xl">
        <UChatPrompt 
            variant="soft" 
            placeholder="Escriba su mensaje aquí..."
        >
            
            
            <template #footer>
                <div class="flex gap-2">
                    <UButton variant="ghost" icon="i-lucide-paperclip" />
                    <USelectMenu v-model="defaultModel" :items="items" variant="soft" class="w-48"></USelectMenu>
                </div>
                <UChatPromptSubmit color="primary" variant="solid" icon="i-lucide-arrow-up" :loading="loadingSubmit" @click="handleSubmit" />
            </template>
        </UChatPrompt>
    </div>
</template>
