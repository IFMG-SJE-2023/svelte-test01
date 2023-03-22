<script>    
import {logado} from '$lib/store.js';
let user;
$: {
    user = $logado;
}
function deslogar(){
    $logado=false;
}
function logar(){

    $logado=true;
    
}
</script>
<nav>
    <a href="/">HOME</a>
    <a href="/cep">CEP</a>
    <a href="/exemplos">EXEMPLOS</a>
    <a href="/sobre">SOBRE</a>
    { #if ($logado===false) } 
        <a href="logar" on:click|preventDefault={logar}>LOGAR</a> 
    { :else} 
        <!-- svelte-ignore a11y-invalid-attribute -->
        <a href="deslogar" on:click|preventDefault={deslogar}>DeSLOGAR</a>
    { /if}
</nav>
<style> 
nav{
    background-color: #9d9;
   padding:1em;

}
a{
    text-decoration: none; 
    margin-right:1em;
}
</style>
<slot />