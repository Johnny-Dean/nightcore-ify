<script lang="ts">
	import { open } from '@tauri-apps/api/dialog';

	let currentAudio: File;

	const loadAudio = async () => {
		try {
			const path = await open({ multiple: false, title: 'Song To Nightcore' });
		} catch (err) {
			console.error(err);
		}
	};
	const playAudio = () => {
		console.log('Playing audio: ', currentAudio);
	};
</script>

<div class="button-container">
	<button on:click={loadAudio}>Open File</button>
</div>

<style>
	.button-container {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 15px;
	}
</style>
