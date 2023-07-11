<svelte:head>
    <link rel="stylesheet" href="/styles/menu.css">
	<title>{pageTitle}</title>
</svelte:head>

<script>
	import { estado } from './Estado.js'
	import { trocarEstadoDoJogo } from './Estado.js'
let pageTitle="Quebra Cabeça";
</script>


<div class="grid-container">

    <div class="img-top">
        <img src="images/Collaboration.gif" alt="fvc">
    </div>

<div class="container">
    <div class="option">
        <button on:click={() => trocarEstadoDoJogo('sobre')}>
            Sobre
        </button>

        <button on:click={() => trocarEstadoDoJogo('ajuda')}>
            Ajuda
        </button>
    </div>

    <div class= nome-qb>
        <h1> Quebra-Cabeça </h1>
        <p>Vamos desafiar suas habilidades cognitivas e raciocínio lógico com nosso site de quebra-cabeças! Junte-se a nós e mergulhe nessa divertida e desafiadora jornada mental!<p>
    </div>

    <div class="jogar">
    <button  on:click={() => trocarEstadoDoJogo('jogar')}> Jogar
    </button>
    </div>
</div>
</div>