<svelte:head>
    <link rel="stylesheet" href="/styles/ajuda.css">
	<title>{pageTitle}</title>
</svelte:head>

<script>
	import { estado } from './Estado.js'
	import { trocarEstadoDoJogo } from './Estado.js'
let pageTitle="Ajuda";
</script>

<div class="container">

    <div class="imgduvida">
        <img src="images/Shrug.gif" alt="">
        </div>

    <div class=tela>
        <h1> PRECISA DE AJUDA?</h1>
        
          <p> Dica: O jogo consiste em organizar 
            as peças na ordem certa e no 
            minímo de tempo possivel 
           clicando em um lugar e 
            logo após o outro até 
            forma a figura original. Boa sorte e bom jogo!</p>


            <div class="butao">
                <button on:click={() => trocarEstadoDoJogo('voltar')}>
                    Voltar
                </button>
            </div>
        </div>
</div>