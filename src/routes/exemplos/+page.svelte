<script>
	import { logado,contador } from '$lib/store.js';
	let texto="";
	let valor ="";



	import TesteBotao from '$lib/TesteBotao.svelte';
	import TesteBotaoEvento from '$lib/TesteBotaoEvento.svelte';
	import BotaoPronto from '$lib/BotaoPronto.svelte';

	function exibirMensagem(e){
		texto=e.detail.texto;
		valor=e.detail.valor;
	}

	function handleClick() {
		alert('Button Clicked');
	}
</script>
<input type="text" bind:value={$contador } />
<TesteBotao  />

<br /><br /><br />
<TesteBotaoEvento on:eventoCustom={exibirMensagem} />
<p>eventoCustom: text={texto} e valor={valor}</p>

<br /><br /><br />
{#if (valor=="") }
	aguardando reseber mensagem
{:else }
	<BotaoPronto  on:click={handleClick} texto="Pode Clicar agora"/>
{/if}