<template>
	<h2>All blog posts list!</h2>
	<section>
		<ul>
			<li
				v-for="post in posts"
				:key="post._path"
			>
				<NuxtLink :to="post._path">{{ post.title }}</NuxtLink>
			</li>
		</ul>
	</section>
</template>

<script setup>
const { data: posts } = await useAsyncData('blog-list', () =>
	queryContent('/blog').only(['_path', 'title']).find()
);
</script>
