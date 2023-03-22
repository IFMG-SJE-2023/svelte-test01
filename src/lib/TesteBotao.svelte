<script>
	import BotaoPronto from '$lib/BotaoPronto.svelte';

	function handleClick() {
		alert('Button Clicked');
	}
</script>

<BotaoPronto on:click={handleClick} texto="Clique me"/>