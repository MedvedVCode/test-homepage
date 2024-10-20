<template>
	<div class="flex space-x-2 items-center">
		<div
			class="text-xs"
			v-if="showNextModeLabel"
		>
			Change to {{ nextMode }}
		</div>
		<button
			@click="toggleColorMode"
			@mouseenter="showNextModeLabel = true"
			@mouseleave="showNextModeLabel = false"
			@focusin="showNextModeLabel = true"
			@focusout="showNextModeLabel = false"
			class="hover:bg-gray-200 dark:hover:bg-gray-400 px-2 py-1"
		>
			{{ nextModeIcon }}
		</button>
	</div>
</template>

<script setup>
const showNextModeLabel = ref(false);
const colorMode = useColorMode();
const modes = ['system', 'light', 'dark'];
const nextModeIcons = {
	system: '☀',
	light: '☼',
	dark: '☽',
};

const nextMode = computed(() => {
	const nextColorModeIndex = modes.indexOf(colorMode.preference) + 1;
	return modes[nextColorModeIndex === modes.length ? 0 : nextColorModeIndex];
});

const nextModeIcon = computed(() => nextModeIcons[nextMode.value]);
const toggleColorMode = () => {
	colorMode.preference = nextMode.value;
};
</script>
