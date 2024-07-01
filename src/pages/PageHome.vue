<script setup lang="ts">
import ExampleBox from '@/components/ExampleBox.vue'
import ExampleLuckyNameGame from '@/examples/ExampleLuckyNameGame.vue'
</script>

<template>
	<ExampleBox>
		<template #title>Lucky Name Game</template>
		<ExampleLuckyNameGame />
	</ExampleBox>
</template>
