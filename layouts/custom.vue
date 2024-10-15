<template>
	<div class="custom">
		<div>This is custom layout</div>
		<slot />
	</div>
</template>

<style scoped>
.custom {
	height: 100vh;
	background-color: teal;
	color: white;
}
</style>
