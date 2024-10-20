<template>
	<NuxtLayout>
		<section>
			<h1 class="text-4xl mb-4 fint-bold">Opps .. {{ error.statusCode }}</h1>
			<p class="text-xl text-gray-500 dark:text-gray-400">{{ error.statusMessage }}</p>
		</section>
	</NuxtLayout>
</template>

<script setup>
	defineProps({
		error: Object
	})
</script>

