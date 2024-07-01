<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { getAll } from '@/api/peopleApi'
import type { Person } from '@/types.ts'

let people = ref<Person[]>([])

const fetchData = async () => {
	try {
		people.value = await getAll()
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
		<li>
			winning names are:
			<span class="font-mono text-orange-900 text-sm">{{
				people.map((m) => m.name).join(', ')
			}}</span>
		</li>
		<li>names are checked with case-sensitivity</li>
	</ul>
	<img class="mt-3 shadow-lg shadow-gray-800" src="/images/luckyname.gif" />
</template>
