<svelte:head>
    <link rel="stylesheet" href="/styles/sobre.css">
	<title>{pageTitle}</title>
</svelte:head>

<script>
	import { estado } from './Estado.js'
	import { trocarEstadoDoJogo } from './Estado.js'
let pageTitle="Sobre nos";
</script>

<div class="container">
    <div class="butao">
        <button on:click={() => trocarEstadoDoJogo('voltar')}>
            Voltar
        </button>
    </div>

    <div class=tela>
        <h1>sobre o jogo  </h1>
    </div>

        <div class="sobre">
            <p class="p-sobre"> Projetado foi feito pelos alunos do instituto Federal de Educação, Ciência e tecnologia de Pernambuco IFPE do campus <span class="left1">Igarassu.
                Do curso tecnico de IPI 1periodo, na diciplina de logica de programação do professor.allan, criado na data </span> <span class="left2"> 06/07/2023
                O foco do projeto é criar um jogo de quebra-cabeças com niveis Facil, Medio, Dificil </span>
             Alunos desenvolvedores do nosso projeto : Gabriel sammy, kauã felix, jeniffer fonseca, jose lucas, pedro lucas</p>
            </div>    
    </div>

        <img  class="tamanhoimg" src="../images/winners.gif" alt="">