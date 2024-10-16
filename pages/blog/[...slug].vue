<template>
	<h2>We are inside the blog post {{route.params.slug}}!</h2>
	<article class="prose dark:prose-invert prose-pre:bg-white dark:prose-pre:bg-gray-800 prose-pre:text-gray-700 dark:prose-pre:text-gray-200">
		<ContentDoc />
	</article>
</template>

<script setup>
const route = useRoute();
</script>
