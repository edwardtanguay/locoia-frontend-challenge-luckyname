<script setup lang="ts">
import ExampleBox from '@/components/DisplayBox.vue'
import ExampleLuckyNameGame from '@/components/ExampleLuckyNameGame.vue'
</script>

<template>
	<ExampleBox>
		<template #title>Lucky Name Game</template>
		<ExampleLuckyNameGame />
	</ExampleBox>
</template>
