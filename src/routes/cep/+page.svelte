<script>
    // import BotaoPronto from "../../lib/BotaoPronto.svelte";
    import BotaoPronto from "$lib/BotaoPronto.svelte";

let {cep,cepNumerico,rua,numero,bairro,cidade,estado}='';

$:{
   cepNumerico = /^[0-9]{8}$/.test(cep);

}

function consultaCep(){

    let url = "https://viacep.com.br/ws/"+cep+"/json/";
    alert(url);
    //return;
    fetch(url)
    .then(response => response.json())
    .then((data) => {
        rua= data.logradouro;
        bairro= data.bairro;
        cidade= data.localidade;
        estado= data.uf;

      });
}
</script>

<div class="container">
<form>
    <label>CEP
        <input  type="text" bind:value={cep} placeholder="digite o cep" />
    </label>
    <br/>
    {#if (cepNumerico===false) }
	    aguardando CEP valido <br/> (apenas numeros)<br/>
    {:else }
        <BotaoPronto  on:click={consultaCep} texto="Consultar CEP"/>
    {/if}
    <br/>
 
    <label>Rua
        <input type="text" bind:value={rua} />
    </label>
    <label>Número
        <input type="text"  bind:value={numero} />
    </label>
    <label>Bairro
        <input type="text" bind:value={bairro} />
    </label>
    <label>Cidade
        <input type="text"  bind:value={cidade} />
    </label>
    <label>Estado
        <input type="text"  bind:value={estado} />
    </label>
</form>
</div>

<style>
    div.container {
        display: flex;
        flex-direction: column;
        height: 80vh;
    }
  form{
    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;
    border: dotted 3px green;
    padding: 0.5em;
    width:50%;
  }    
    label{
        
        display:flex;
        flex-direction: column;
        margin-top:0.1em;


    }

</style>