<script lang="ts">
	import { createEventDispatcher, onMount } from 'svelte';
	export let once = false;
	export let pause = false;
	export let top = 0;
	export let bottom = 0;
	export let left = 0;
	export let right = 0;
	const dispatch = createEventDispatcher();
	let intersecting = false;
	let container: HTMLDivElement;
	let threshold: number | Array<number> = 1;
	export let root: HTMLElement | null = null;

	onMount(() => {
		if (typeof IntersectionObserver !== 'undefined') {
			const rootMargin = `${bottom}px ${left}px ${top}px ${right}px`;

			const observer = new IntersectionObserver(
				(entries) => {
					intersecting = entries[0].isIntersecting;
					dispatch('intersectionChange', intersecting);
					if (intersecting && !pause) {
						dispatch('intersect');
					}
					if (intersecting && once) {
						observer.unobserve(container);
					}
				},
				{
					root,
					rootMargin,
					threshold
				}
			);

			observer.observe(container);
			return () => observer.unobserve(container);
		}

		function handler() {
			const bcr = container.getBoundingClientRect();
			intersecting =
				bcr.bottom + bottom > 0 &&
				bcr.right + right > 0 &&
				bcr.top - top < (root ? root.offsetHeight : window.innerHeight) &&
				bcr.left - left < (root ? root.offsetWidth : window.innerHeight);

			if (intersecting && once) {
				root
					? root.removeEventListener('scroll', handler)
					: window.removeEventListener('scroll', handler);
			}
		}

		root ? root.addEventListener('scroll', handler) : window.addEventListener('scroll', handler);
		return () =>
			root
				? root.removeEventListener('scroll', handler)
				: window.removeEventListener('scroll', handler);
	});
</script>

<div bind:this={container} {...$$props}>
	<slot {intersecting} />
</div>

<style scoped>
	div {
		width: 100%;
		height: 10px;
	}
</style>
