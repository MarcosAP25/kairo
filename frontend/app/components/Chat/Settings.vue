<template>
    <div>
        <UModal>
            <UButton
                icon="i-lucide-settings"
                color="neutral"
                variant="ghost"
                aria-label="Settings"
                
            />
            
            <template #header>
                <UButton
                    icon="i-lucide-x"
                    color="neutral"
                    variant="ghost"
                    aria-label="Settings"
                />
            </template>
            <template #body>
                <div class="flex h-56">
                    <ChatSettingsOptions />
                    <ChatSettingsModels />
                </div>
            </template>
        </UModal>
    </div>
</template>
