<script setup lang="ts">
import { reactive, onMounted } from 'vue'
import { getAll } from '@/api/peopleApi'
import type { Person } from '@/types.ts'

let people = reactive<Person[]>([])

const fetchData = async () => {
	try {
		people = await getAll()
	} catch (err: any) {
		throw new Error(err.message)
	}
}

onMounted(() => {
	fetchData()
})
</script>
<template>
	<p class="mb-2">This is a coding challenge created by Edward Tanguay for Locoia, July 2024.</p>
	<p>
		For technical information, see the
		<a
			class="underline"
			href="https://github.com/edwardtanguay/locoia-frontend-challenge-luckyname"
			target="_blank"
			>GitHub repo</a
		>.
	</p>
	<h2 class="text-2xl mt-3 mb-1">Instructions</h2>
	<ul class="list-disc ml-4">
		<li>type in any name and press ENTER</li>
		<li>if you enter a lucky name, you win a prize, which you can accept or reject</li>
		<li>winning names are: {{ people.map((m) => m.name).join(', ') }}</li>
		<li>names are checked with case-sensitivity</li>
	</ul>
</template>
