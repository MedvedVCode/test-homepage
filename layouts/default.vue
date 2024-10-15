<template>
	<div class="container mx-auto max-w-2xl">
		<header class="flex justify-between items-center my-4">
			<div>
				<NuxtLink
					to="/"
					class="text-xl font-semibold p-2 hover:bg-gray-200"
					>MedvedVCode</NuxtLink
				>
			</div>
			<Menu />
		</header>
		<main class="p-2">
			<slot />
		</main>
	</div>
</template>

<script setup>
useHead({
	titleTemplate: '%s | MedvedVCode',	
})
</script>
