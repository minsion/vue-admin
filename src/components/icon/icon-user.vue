<template>
    <svg v-if="!fill" width="18" height="18" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="12" cy="6" r="4" stroke="currentColor" stroke-width="1.5" />
        <path
            opacity="0.5"
            d="M20 17.5C20 19.9853 20 22 12 22C4 22 4 19.9853 4 17.5C4 15.0147 7.58172 13 12 13C16.4183 13 20 15.0147 20 17.5Z"
            stroke="currentColor"
            stroke-width="1.5"
        />
    </svg>
    <svg v-else width="18" height="18" viewBox="0 0 18 18" fill="none">
        <circle cx="9" cy="4.5" r="3" fill="currentColor" />
        <path
            opacity="0.5"
            d="M15 13.125C15 14.989 15 16.5 9 16.5C3 16.5 3 14.989 3 13.125C3 11.261 5.68629 9.75 9 9.75C12.3137 9.75 15 11.261 15 13.125Z"
            fill="currentColor"
        />
    </svg>
</template>
<script lang="ts" setup>
    defineProps({
        fill: {
            type: Boolean,
            default: false,
        },
    });
</script>
