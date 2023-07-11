<script>
	// importa os componentes que representam os elementos gráficos do jogo
	import Dificuldades from "./Dificuldades.svelte";
	import Sobre from "./Sobre.svelte";
	import Menu from "./Menu.svelte";
	import Ajuda from "./Ajuda.svelte";
	import JogarFacil from "./JogarFacil.svelte";
	import JogarMedio from "./JogarMedio.svelte";
	import JogarDificil from "./JogarDificil.svelte";

	// importa um "writable" que funciona como uma variável global, todos os módulos que a importarem poderão ver o seu valor
	import { estado } from "./Estado.js";
</script>

<!-- Esta não é a melhor forma de criar rotas em um projeto.
 Mais detalhes sobre como criar rotas em:
 https://kit.svelte.dev/docs/routing
 https://www.npmjs.com/package/svelte-routing
 https://www.npmjs.com/package/svelte-router-spa  -->

<!-- o jogo tem três estados menu, jogar e sobre, cada um representa uma tela diferente para o usuário -->
{#if $estado === "menu"}
	<!-- notem como cada componente/módulo que crianos no svelte vira um tag -->
	<Menu />
{:else if $estado === "sobre"}
	<Sobre />
{:else if $estado === "jogar"}
	<Dificuldades />
{:else if $estado === "ajuda"}
	<Ajuda />
{:else if $estado === "voltar"}
	<Menu />
{:else if $estado === "facil"}
	<JogarFacil />
{:else if $estado === "medio"}
	<JogarMedio />
{:else if $estado === "dificil"}
	<JogarDificil />
{:else if $estado === "voltarr"}
	<Dificuldades />
{:else if $estado === "proxima_fase1"}
	<JogarMedio />
	{:else if $estado === "proxima_fase2"}
	<JogarDificil />
{/if}
