<template>
	<!-- <div>
		<h2 class="text-2xl font-semibold mb-10">Projects</h2>
		<ProjectList />
	</div> -->
	<article class="prose dark:prose-invert">
		<ContentDoc path="/projects" />
	</article>
</template>

<script setup>
useSeoMeta({
	title: 'Projects',
});
</script>