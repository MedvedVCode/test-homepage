<template>
	<h2>All blog posts list!</h2>
	<div>
		<button @click="enableCustomLayout">Update layout</button>
	</div>
</template>

<script setup>
const enableCustomLayout = () => {
	const layout = useRoute().meta.layout;
	setPageLayout(layout === 'custom' ? 'another' : 'custom');
};
// definePageMeta({
// 	layout: false,
// });
</script>
