<svelte:head>
	<link rel="stylesheet" href="/styles/dificuldade.css">
</svelte:head>

<script>
	import { estado } from "./Estado.js"
	import { trocarEstadoDoJogo } from './Estado.js'
	</script>

    <div class="imag_flex">
        <img src="images/hinkintg face.gif" alt="">
  
        <img class="new-idea" src="images/New idea.gif" alt="">
    </div>

<div class=geral>
    <h1>Escolha o nivel da dificuldade </h1>
        
    <div class=facil>
        <button class='bnt bnt-1' on:click={() => trocarEstadoDoJogo('facil')}>
            facil
        </button>
        </div>
      
        <div class=medio>
            <button class='bnt bnt-2' on:click={() => trocarEstadoDoJogo('medio')}> 
                Medio </button>
        </div>
            
        <div class=dificil>
            <button class='bnt bnt-3' on:click={() => trocarEstadoDoJogo('dificil')}>
                Dificil </button>
        </div>

    <div class="voltar">
        <button class="btn btn-4" on:click={() => trocarEstadoDoJogo('voltar')}>
            Voltar 
        </button>
    </div>
</div>