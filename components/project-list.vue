<template>
	<p class="mb-10">Take a look at my GitHub projects!</p>
	<section v-if="pending">Loading...</section>
	<section v-else-if="error">{{ error }}</section>
	<section v-else>
		<ul class="grid grid-col-1 gap-4">
			<li
				v-for="repo in repos"
				:key="repo.id"
				class="border border-gray-200 rounded-sm p-4 hover:bg-gray-100 font-mono"
			>
				<a
					:href="repo.html_url"
					target="_blank"
					class="cursor-pointer"
				>
					<div class="flex items-center justify-between">
						<div class="font-semobold hover:text-teal-400">{{ repo.name }}</div>
						<div class="hover:text-teal-400">{{ repo.stargazers_count }} ★</div>
					</div>
					<p class="text-gray-500 text-sm">{{ repo.description }}</p>
				</a>
			</li>
		</ul>
	</section>
</template>

<script setup>
const { error, pending, data } = await useFetch(
	'https://api.github.com/users/MedvedVCode/repos'
);
const repos = computed(() =>
	data.value
		// .filter((repo) => repo.description)
		.sort((a, b) => b.stargazers_count - a.stargazers_count)
);
</script>
