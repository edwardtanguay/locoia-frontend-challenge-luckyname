<script setup lang="ts">
defineProps<{
	title: string
	subtitle: string
}>()
</script>

<template>
	<h1 class="text-2xl">{{ title }}</h1>
	<h2 class="mb-2 italic text-sm">{{ subtitle }}</h2>
</template>
