<svelte:head>
	<link rel="stylesheet" href="/styles/jogar_medio.css" />
	<title>{pageTitle}</title>
</svelte:head>

<script>
	import { construct_svelte_component } from "svelte/internal";

	import { estado } from "./Estado.js";
	import { trocarEstadoDoJogo } from "./Estado.js";
	let pageTitle = "Quebra cabeça nivel facil";

	let linha = false;
	let coluna = false;
	let venceu = false;
	// let peca = ["../src/static/row-1-column-1.jpg"]
	function selecionarPeca(pc, i, j) {
		console.log(i, j);
		if (primeiro === false) {
			primeiro = pc;
			linha = i;
			coluna = j;
		} else {
			segundo = pc;
			// console.log("peça 1:", primeiro);
			// console.log("peça 2:", segundo);
			trocarPosicao(primeiro, segundo, i, j);
			primeiro = false;
			segundo = false;
		}
	}

	function trocarPosicao(p1, p2, i, j) {
		let temporal = p1;
		pecas[linha][coluna] = p2;
		pecas[i][j] = temporal;
		linha = false;
		coluna = false;
		testarArray();
		console.log(pecas);
	}

	let primeiro = false;
	let segundo = false;

	let pecas = [
		[
            { image: "bobesponja/3.jpg", value: 14},
			{ image: "bobesponja/11.jpg", value: 6 },
			{ image: "bobesponja/14.jpg", value: 3 },
            { image: "bobesponja/13.jpg", value: 4 }
		],
		[
			{ image: "bobesponja/12.jpg", value: 5 },
			{ image: "bobesponja/10.jpg", value: 7 },
            { image: "bobesponja/15.jpg", value: 2 },
            { image: "bobesponja/7.jpg", value: 10 },
            
		],
		[
			{ image: "bobesponja/8.jpg", value: 9},
            { image: "bobesponja/1.jpg", value: 16},
            { image: "bobesponja/5.jpg", value: 12 },
            { image: "bobesponja/9.jpg", value: 8}
		],
        [
			{ image: "bobesponja/4.jpg", value: 13 },
			{ image: "bobesponja/16.jpg", value: 1},
			{ image: "bobesponja/2.jpg", value: 15},
            { image: "bobesponja/6.jpg", value: 11 },
		],
	];

	console.log(pecas[0]);
	// let pecas = [

	// 	[{image: "", value: 5},{image: "", value: 2},{image: "", value: 7}],
	// 	[{image: "", value: 4},{image: "", value: 1},{image: "", value: 9}],
	// 	[{image: "", value: 8},{image: "", value: 3},{image: "", value: 6}],
	// 	[{image: "", value: 10},{image: "", value: 12},{image: "", value: 11}],
	// 	[{image: "", value: 13},{image: "", value: 14},{image: "", value: 15}],
	// 	[{image: "", value: 18},{image:"", value: 17},{image: "", value: 16}]
	//   ];

	let arrayCorreto = [
		[
			{ image: "", value: 1 },
			{ image: "", value: 2 },
			{ image: "", value: 3 },
            { image: "", value: 4 }
		],
		[
			{ image: "", value: 5 },
			{ image: "", value: 6 },
			{ image: "", value: 7 },
            { image: "", value: 8 }
		],
		[
			{ image: "", value: 9 },
			{ image: "", value: 10 },
			{ image: "", value: 11},
            { image: "", value: 12}
		],
        [
			{ image: "", value: 13},
			{ image: "", value: 14},
			{ image: "", value: 15},
            { image: "", value: 16}
		],
	];

	// let arrayCorreto = [
	//   [{image: "", value: 1},{image: "", value: 2},{image: "", value: 3}],
	//   [{image: "", value: 4},{image: "", value: 5},{image: "", value: 6}],
	//   [{image: "", value: 7},{image: "", value: 8},{image: "", value: 9}],
	//   [{image: "", value: 10},{image:"", value:11},{image:"", value: 12}],
	//   [{image: "", value: 13},{image:"", value: 14},{image:"", value: 15}],
	//   [{image: "", value: 16},{image:"", value: 17},{image: "", value: 18}]
	// ];

	function testarArray() {
		for (let i = 0; i < pecas.length; i++) {
			for (let j = 0; j < pecas[i].length; j++) {
				if (pecas[i][j].value !== arrayCorreto[i][j].value) {
					console.log("Não cabo !!");
					return;
				}
			}
		}
		return (venceu = true);
	}
</script>

<div class="butao">
	<button on:click={() => trocarEstadoDoJogo("voltarr")}> Voltar </button>
</div>

<main>
	{#if venceu}
	<h1> Parabénssss!!! </h1>
	{/if}
	<br>
	<br>


	<table class="jogo">
		{#each pecas as row, i}
			{#each row as peca, j}
				<div class="table">
					<!-- svelte-ignore a11y-click-events-have-key-events -->
					<!-- svelte-ignore a11y-no-static-element-interactions -->
					<img
						class="peca"
						src={peca.image}
						on:click={() => {
							selecionarPeca(peca, i, j);
						}}
						alt=""
					/>
				</div>
			{/each}
		{/each}
	</table>

	{#if venceu}
		<div class="proximafase">
			<button on:click={() => trocarEstadoDoJogo("proxima_fase2")}>
				Ir para a proxima fase
			</button>
		</div>
	{/if}

</main>


