<template>
	<div class="another">
		<div>This is another layout</div>
		<slot />
	</div>
</template>

<style>
body{
	font-family: 'Roboto', sans-serif;
}
.another {
	height: 100vh;
	background-color: tomato;
	color: white;
}
</style>

<script setup>
useHead({
	titleTemplate: '%s | MedvedVCode',
	link: [
    {
      rel: 'preconnect',
      href: 'https://fonts.googleapis.com'
    },
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=Roboto&display=swap',
      crossorigin: ''
    }
  ]
});
</script>
