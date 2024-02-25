<template>
    <ul>
        <a :href=route class="h-12 w-full ps-5 flex items-center hover:bg-slate-200 hover:opacity-50 rounded-2xl">
            <ion-icon :name=icon></ion-icon>
            <span v-if="!hideTitle" class="ps-4">{{ title }}</span>
        </a>
    </ul>
</template>

<script setup>
const props = defineProps({
    title: {
        required: true,
        type: String,
    },
    icon: {
        required: true,
        type: String,
    },
    route: {
        required: true,
        type: String
    },
    hideTitle: Boolean
})
</script>