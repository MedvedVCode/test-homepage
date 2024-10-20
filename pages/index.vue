<template>
	<article class="prose dark:prose-invert max-w-none">
		<ContentDoc path="/" />
	</article>
</template>

<script setup>
useSeoMeta({
	title: 'Main Page',
	description: 'This is main page',
	ogTitle: 'Main Page',
});

useHead({
	htmlAttrs: {
		lang: 'en',
	},
	link: [
		{
			rel: 'icon',
			type: 'image/svg+xml',
			href: '/logo.svg',
		},
	],
});
</script>

