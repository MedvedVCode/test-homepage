<template>
	<h2>We are inside the blog post {{route.params.slug}}!</h2>
	<article class="prose dark:prose-invert">
		<ContentDoc />
	</article>
</template>

<script setup>
const route = useRoute();
</script>
