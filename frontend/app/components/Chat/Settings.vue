
<script lang="ts" setup>
 const open = ref(false);
  const currentOptionSelected = ref('Prompt Preferences');
  
  
  const handleOptionChange = (option: string, label: string) => {
    currentOptionSelected.value = label;
  };
  
  const toggleModal = () => {
    open.value = !open.value;
    console.log('modal state', open.value)
  };
  
</script>
<template>
    <div>
        <UModal v-model:open="open" :ui="{ content: 'sm:max-w-3xl' }">
            <UButton
                icon="i-lucide-settings"
                color="neutral"
                variant="ghost"
                aria-label="Settings"
            />
            
            <template #header>
                <div class="w-3xs">
                    <UButton
                        icon="i-lucide-x"
                        color="neutral"
                        variant="ghost"
                        aria-label="Close"
                        @click="toggleModal"
                    />
                </div>
                    <h2 class="">{{ currentOptionSelected }}</h2>
            </template>
            <template #body>
                <div class="flex gap-3">
                    <div class="w-3xs">
                        <ChatSettingsOptions 
                            @optionChange="handleOptionChange"
                        />
                    </div>
                    <ChatSettingsModels />
                </div>
            </template>
        </UModal>
    </div>
</template>
