<script lang="ts">
	import CalendarWeddingDate from '../components/calendar-wedding-date.svelte';
	import InvitationMessage from '../components/invitation-message.svelte';
	import PhotoGallery from '../components/photo-gallery.svelte';
	import TopCover from '../components/top-cover.svelte';
	import WeddingLocation from '../components/wedding-location.svelte';

const images = [
            {
              largeURL:
                'https://cdn.photoswipe.com/photoswipe-demo-images/photos/1/img-2500.jpg',
              thumbnailURL:
                'https://cdn.photoswipe.com/photoswipe-demo-images/photos/1/img-200.jpg',
              width: 2000,
              height: 2500,
            },
            {
              largeURL:
                'https://cdn.photoswipe.com/photoswipe-demo-images/photos/2/img-2500.jpg',
              thumbnailURL:
                'https://cdn.photoswipe.com/photoswipe-demo-images/photos/2/img-200.jpg',
              width: 2500,
              height: 2500,
            },
            {
              largeURL:
                'https://cdn.photoswipe.com/photoswipe-demo-images/photos/3/img-2500.jpg',
              thumbnailURL:
                'https://cdn.photoswipe.com/photoswipe-demo-images/photos/3/img-200.jpg',
              width: 2500,
              height: 1666,
            },
          ]
</script>

<TopCover />
<InvitationMessage />
<PhotoGallery galleryID="wedding-gallery" {images} />
<CalendarWeddingDate />
<WeddingLocation />
