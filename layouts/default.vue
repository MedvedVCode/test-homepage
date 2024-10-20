<template>
	<div class="container mx-auto max-w-4xl">
		<header class="flex justify-between items-center my-4">
			<div class="flex items-center space-x-12">
				<div>
					<NuxtLink
						to="/"
						class="text-xl font-semibold p-2 hover:bg-gray-200 uppercase dark:hover:bg-gray-800"
					>
						MedvedVCode
					</NuxtLink>
				</div>
				<Menu />
			</div>
			<ClientOnly>
				<ColorModeSelector />
			</ClientOnly>
		</header>
		<main class="p-2 mt-10">
			<slot />
		</main>
	</div>
</template>

<script setup>
useHead({
	titleTemplate: '%s | MedvedVCode',
});
</script>

<style>
body {
	font-family: 'Roboto', sans-serif;
}
body {
	@apply bg-white	dark:bg-gray-900 text-gray-700 dark:text-gray-300;
}
</style>
