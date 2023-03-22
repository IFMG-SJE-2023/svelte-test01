<script>
    import { logado,contador } from '$lib/store.js';
</script>
<p>...Sobre o site...</p>
<p>usuário  logado? {$logado ? 'sim' : 'nao'}</p>
<p>contador é {$contador}</p>
<p>var $logado é {$logado}</p>
