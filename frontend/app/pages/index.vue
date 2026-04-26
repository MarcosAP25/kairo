<script lang="ts" setup>
  const open = ref(true);
</script>

<template>
    <div class="flex flex-1  h-dvh">
        <!-- Sidebar lateral -->
        <MainSidebar v-model:open="open" />
        
        <div class="flex-1 flex flex-col overflow-hidden m-4 ml-4 ms-0 rounded-xl shadow-sm ring ring-default bg-default">
            <div class="h-(--ui-header-height) shrink-0 flex items-center px-4">
                <UButton
                    icon="i-lucide-panel-left"
                    color="neutral"
                    variant="ghost"
                    aria-label="Toggle sidebar"
                    @click="open = !open"
                />
                <div class="flex items-center ms-auto">
                    <UButton
                        icon="i-lucide-settings"
                        color="neutral"
                        variant="ghost"
                        aria-label="Settings"
                        
                    />
                </div>
            </div>
            
            <!-- Content principal -->
            <div class="flex p-4 size-full items-center justify-center">
                <ChatPromt></ChatPromt>
            </div>
        </div>
    </div>
</template>
