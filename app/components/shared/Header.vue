<script setup lang="ts">
import type { NavigationMenuItem } from '@nuxt/ui'

const route = useRoute()

const items = computed<NavigationMenuItem[]>(() => [{
    label: 'Products',
    to: '/products',
    icon: 'i-lucide-box',
    active: route.path.startsWith('/products')
}, {
    label: 'Pricing',
    to: '/pricing',
    icon: 'i-lucide-tag',
    active: route.path.startsWith('/pricing')
}, {
    label: 'About',
    to: '/about',
    icon: 'i-lucide-info',
    active: route.path.startsWith('/about')
}, {
    label: 'Contact',
    to: '/contact',
    icon: 'i-lucide-mail',
    active: route.path.startsWith('/contact')
}])

const responsiveMenu = ref([
    ...items.value,
    {
        label: 'Login',
        icon: 'i-lucide-log-in',
        active: route.path.startsWith('/login'),
        to: '/login'
    }
]); 
</script>

<template>
    <UHeader>
        <template #title>
            <IconsNuxtui class="h-6 w-auto" />
        </template>

        <UNavigationMenu :items="items" />

        <template #right>
            <UColorModeButton />

            <UTooltip text="Open on GitHub" :kbds="['meta', 'G']">
                <UButton color="neutral" variant="ghost" to="https://github.com/nuxt/ui" target="_blank"
                    icon="i-simple-icons-github" aria-label="GitHub" />
            </UTooltip>
            <UButton label="Sign in" color="primary" to="/login" />
        </template>

        <template #body>
            <UNavigationMenu :items="responsiveMenu" orientation="vertical" class="-mx-2.5" />
        </template>
    </UHeader>
</template>