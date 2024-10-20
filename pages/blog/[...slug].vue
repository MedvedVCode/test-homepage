<template>
	<article
		class="prose dark:prose-invert prose-pre:bg-white dark:prose-pre:bg-gray-800 prose-pre:text-gray-700 max-w-none dark:prose-pre:text-gray-200"
	>
		<ContentDoc>
			<template #not-found>
				<h1 class="uppercase">404. Not found</h1>
				<p>We couldn't find the blog post you were looking for.</p>
			</template>
			<template v-slot="{ doc }">
				<div class="grid grid-cols-6 gap-16">
					<div :class="{ 'col-span-4': doc.toc, 'col-span-6': !doc.toc }">
						<ContentRenderer :value="doc" />
					</div>
					<div
						class="col-span-2 not-prose"
						v-if="doc.toc"
					>
						<aside class="sticky top-8">
							<div class="font-semibold mb-2">Table of Contents</div>
							<nav>
								<TocLinks
									:links="doc.body.toc.links"
									:active-id="activeId"
								/>
							</nav>
						</aside>
					</div>
				</div>
			</template>
		</ContentDoc>
	</article>
</template>

<script setup>
const activeId = ref(null);

onMounted(() => {
	let elements = [];
	const callback = (entries) => {
		// console.log(entries);
		for (const entry of entries) {
			if (entry.isIntersecting) {
				activeId.value = entry.target.id;
				break;
			}
		}
	};
	const observer = new IntersectionObserver(callback, {
		root: null,
		threshold: 0.5,
	});
	
	setTimeout(() => {
		elements = document.querySelectorAll('h2, h3');
		for (const element of elements) {
			observer.observe(element);
		}
	}, 150);

	onBeforeUnmount(() => {
		// observer.disconnect();
		for (const element of elements) {
			observer.unobserve(element);
		}
	});
});
</script>
