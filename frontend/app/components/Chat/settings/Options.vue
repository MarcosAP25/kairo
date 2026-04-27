<script lang="ts" setup>

const currentOption = ref<string>('promptPreferences');

function handleOptionChange(option: string, label: string) {
    currentOption.value = option;
    emit('optionChange', option, label);
}

const emit = defineEmits(['optionChange']);
</script>
<template>
    <div>
        <UPageList>
            <UButton 
                label="Prompt Preferences"
                name="promptPreferences"
                variant="ghost"
                activeVariant="soft"
                class="button-list"
                :active="currentOption === 'promptPreferences'"
                @click="handleOptionChange('promptPreferences', 'Prompt Preferences')"
            ></UButton>
            <UButton 
                label="LLM Providers"
                name="llmProviders"
                variant="ghost"    
                activeVariant="soft"
                class="button-list"
                :active="currentOption === 'llmProviders'" 
                @click="handleOptionChange('llmProviders', 'LLM Providers')"
            ></UButton>
        </UPageList>
    </div>
</template>

<style scoped>
    .button-list{
        margin-bottom: 1rem;
    }
</style>
