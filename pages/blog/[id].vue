<template>
	<h2>We are inside the blog!</h2>
	<div>Router ID is "{{ route.params.id }}"</div>
	<div>Full router path is "{{ route.fullPath }}"</div>
</template>

<script setup>
const route = useRoute();
</script>
