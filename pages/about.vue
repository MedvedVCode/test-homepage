<template>
	<article class="prose dark:prose-invert max-w-none">
		<ContentDoc path="/about" />
	</article>
</template>

<script setup>
definePageMeta({
	layout: 'default',
});
useSeoMeta({
	title: 'About Page',
	description: 'This is About page',
	ogTitle: 'About Page',
});
</script>
