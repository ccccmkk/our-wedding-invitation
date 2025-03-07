<script lang="ts">
	import { onMount } from 'svelte';
	import PhotoSwipeLightbox from 'photoswipe/lightbox';
	import 'photoswipe/style.css';
	import { localeStore } from '../i18n.svelte';
	export let galleryID;
	export let images;

	onMount(() => {
		let lightbox = new PhotoSwipeLightbox({
			gallery: '#' + galleryID,
			children: 'a',
			pswpModule: () => import('photoswipe')
		});
		lightbox.init();
	});
</script>

<section class="photo-gallary section-max-width">
	<div>
		{#if localeStore.isKr}
			<h2 class="gallery-title kr">Gallery</h2>
			<p class="gallery-description kr">사진을 클릭하시면 크게보실 수 있습니다.</p>
		{:else}
			<h2 class="gallery-title en">Gallery</h2>
			<p class="gallery-description en">
				If you click the photo, you can view it in a larger size.
			</p>
		{/if}
	</div>
	<div class="pswp-gallery" id={galleryID}>
		{#each images as image}
			<a
				class="grid-view-item"
				href={image.largeURL}
				data-pswp-width={image.width}
				data-pswp-height={image.height}
				target="_blank"
				rel="noreferrer"
			>
				<img class="preview-img" src={image.thumbnailURL} alt="" />
			</a>
		{/each}
	</div>
</section>

<style lang="scss">
	.photo-gallary {
		padding: 60px 24px;

		.gallery-title {
			color: $primary-color;
		}
		.gallery-description {
			&.kr {
				line-height: 2.3em;
				font-size: 0.9rem;
			}
			&.en {
				line-height: 1.8em;
				font-size: 1.1rem;
			}
		}

		.preview-img {
			border-radius: 4px;
			border: 1px solid #eaeaea;
		}
	}
</style>
