<script>
	import { createEventDispatcher } from 'svelte';
	const despachar = createEventDispatcher();

	function CliqueBotao() {
		despachar(
            'eventoCustom', 
            {
			    texto: 'Fulano',
                valor: 123
		    }
        );
	}

    import BotaoPronto from '$lib/BotaoPronto.svelte';
</script>

<BotaoPronto on:click={CliqueBotao} texto="clique para receber msg" />