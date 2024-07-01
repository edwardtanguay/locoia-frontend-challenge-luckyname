<script setup lang="ts">
import ExampleBox from '@/components/DisplayBox.vue'
import ExampleLuckyNameGame from '@/components/LuckyNameGame.vue'
</script>

<template>
	<ExampleBox>
		<template #title>Lucky Name Game</template>
		<ExampleLuckyNameGame />
	</ExampleBox>
</template>
