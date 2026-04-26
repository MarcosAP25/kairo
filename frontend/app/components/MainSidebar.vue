<script setup lang="ts">
import type { NavigationMenuItem, SidebarProps } from "@nuxt/ui";

const props = defineProps({
  open: {
    type: Boolean,
    default: true,
  },
});

const emit = defineEmits(['update:open']);
</script>

<template>
    <div class="">
        <USidebar
            :open="props.open"
            variant="inset"
            collapsible="offcanvas"
            side="left"
            :ui="{
                container: 'h-full',
            }"
        >
            <template #header>
                <img src="/logo.svg" alt="Logo" class="size-8" />
                <span class="flex-1 text-2xl font-bold">Kairo</span>
                <div class="flex align-items-center ms-auto">
                    <UButton
                        icon="i-lucide-search"
                        color="neutral"
                        variant="ghost"
                        aria-label="Toggle sidebar"
                        @click="emit('update:open', !props.open)"
                    />
                </div>
            </template>
            
            <template #default>
                <UButton
                    icon="i-lucide-plus"
                    color="primary"
                    variant="soft"
                    aria-label="New chat"
                    label="New chat"
                    :ui="{
                        base: 'flex justify-center py-2',
                    }"
                    @click=""
                />
            </template>
            
            <template #footer>
                <div class="flex justify-center w-full">
                    <UButton
                        icon="i-lucide-log-in"
                        color="primary"
                        variant="ghost"
                        aria-label="Sign In"
                        label="Sign In"
                        :ui="{
                            base: 'flex justify-center py-2',
                        }"
                        @click=""
                    />
                </div>
            </template>
        </USidebar>
    </div>
</template>
