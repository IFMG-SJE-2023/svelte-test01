<script>
	export let texto='Clique';
	export let desativado=''; 

</script>
<button on:click  {desativado}>
	{texto}
</button>

<style>	
	button{
		background: #105702;
		color: #fff;
		border: unset;
		border-radius: 6px;
		padding: .75rem 1.5rem;
		cursor: pointer;
	}
	button:hover {
		background: #0b68db;
		color: #ffffff;
	}

</style>