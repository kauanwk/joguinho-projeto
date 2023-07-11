<svelte:head>
    <link rel="stylesheet" href="/styles/jogar_dificil.css" />
    <title>{pageTitle}</title>
</svelte:head>

<script>
    import { estado } from "./Estado.js";
    import { trocarEstadoDoJogo } from "./Estado.js";
    let pageTitle = "Quebra cabeça nivel Dificil";

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
        jogoAtual[linha][coluna] = p2;
        jogoAtual[i][j] = temporal;
        linha = false;
        coluna = false;
        testarArray();
        console.log(jogoAtual);
        console.log(arrayCorreto);
    }

    let primeiro = false;
    let segundo = false;

    let pecas = [
        [
            { image: "/pastaMedio/1.png", value: 36 },
            { image: "/pastaMedio/7.png", value:30},
            { image: "/pastaMedio/13.png", value: 24 },
            { image: "/pastaMedio/19.png", value: 18 },
            { image: "/pastaMedio/25.png", value: 12 },
            { image: "/pastaMedio/31.png", value: 6 },
        ],
        [
            { image: "/pastaMedio/2.png", value: 35 },
            { image: "/pastaMedio/8.png", value: 29 },
            { image: "/pastaMedio/14.png", value:23 },
            { image: "/pastaMedio/20.png", value: 17 },
            { image: "/pastaMedio/26.png", value: 11 },
            { image: "/pastaMedio/32.png", value: 5 },
        ],
        [
            { image: "/pastaMedio/3.png", value: 34 },
            { image: "/pastaMedio/9.png", value: 28 },
            { image: "/pastaMedio/15.png", value: 22 },
            { image: "/pastaMedio/21.png", value: 16 },
            { image: "/pastaMedio/27.png", value: 10 },
            { image: "/pastaMedio/33.png", value: 4 },
        ],
        [
            { image: "/pastaMedio/4.png", value: 33},
            { image: "/pastaMedio/10.png", value: 27 },
            { image: "/pastaMedio/16.png", value: 21 },
            { image: "/pastaMedio/22.png", value: 15 },
            { image: "/pastaMedio/28.png", value: 9 },
            { image: "/pastaMedio/34.png", value: 3 },
        ],
        [
            { image: "/pastaMedio/5.png", value: 32 },
            { image: "/pastaMedio/11.png", value: 26 },
            { image: "/pastaMedio/17.png", value: 20 },
            { image: "/pastaMedio/23.png", value: 14 },
            { image: "/pastaMedio/29.png", value: 8 },
            { image: "/pastaMedio/35.png", value: 2 },
        ],
        [
            { image: "/pastaMedio/6.png", value: 31 },
            { image: "/pastaMedio/12.png", value: 25 },
            { image: "/pastaMedio/18.png", value: 19 },
            { image: "/pastaMedio/24.png", value: 13 },
            { image: "/pastaMedio/30.png", value: 7 },
            { image: "/pastaMedio/36.png", value: 1 },
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
            { image: "", value: 4 },
            { image: "", value: 5 },
            { image: "", value: 6 },
        ],
        [
            { image: "", value: 7 },
            { image: "", value: 8 },
            { image: "", value: 9 },
            { image: "", value: 10 },
            { image: "", value: 11 },
            { image: "", value: 12 },
        ],
        [
            { image: "", value: 13 },
            { image: "", value: 14 },
            { image: "", value: 15 },
            { image: "", value: 16 },
            { image: "", value: 17 },
            { image: "", value: 18 },
        ],
        [
            { image: "", value: 19 },
            { image: "", value: 20 },
            { image: "", value: 21 },
            { image: "", value: 22 },
            { image: "", value: 23 },
            { image: "", value: 24 },
        ],
        [
            { image: "", value: 25 },
            { image: "", value: 26 },
            { image: "", value: 27 },
            { image: "", value: 28 },
            { image: "", value: 29 },
            { image: "", value: 30 },
        ],
        [
            { image: "", value: 31 },
            { image: "", value: 32 },
            { image: "", value: 33 },
            { image: "", value: 34 },
            { image: "", value: 35 },
            { image: "", value: 36 },
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
        return venceu = true;
    }

    let jogoAtual = pecas;
    // let arrayMedio = [
    // 	[{image: "", value: 1},{image: "",value: 7},{image: "", value: 13},{image: "", value: 19},{image: "", value: 25},{image: "/src/lib/images/pastaMedio/31.png", value: 31}],
    // 	[{image: "", value: 2},{image: "", value: 8},{image:"", value: 14},{image: "", value: 20},{image: "", value: 26},{image: "//32.png", value: 32}],
    // 	[{image: "", value: 3},{image: "", value: 9},{image: "", value: 15},{image: "", value: 21},{image: "", value: 27},{image: "//33.png", value: 33}],
    // 	[{image: "", value: 4},{image: "", value: 10},{image: "", value: 16},{image: "", value: 22},{image: "", value: 28},{image: "//34.png", value: 34}],
    // 	[{image: "", value: 5},{image: "", value: 11},{image: "", value: 17},{image: "", value: 23},{image: "", value: 29},{image: "//35.png", value: 35}],
    // 	[{image: "", value: 6},{image: "", value: 12},{image: "", value: 18},{image: "", value: 24},{image: "", value: 30},{image: "/src/lib/im6}],

    // ]
</script>

<div class="butao">
    <button on:click={() => trocarEstadoDoJogo("voltarr")}> Voltar </button>
</div>

<main>

    {#if venceu}
    <h1>Parabénssss! Voce concluíu todos os níveis!!</h1>
    {/if}

    <!-- <table
        class="jogo"
        style="grid-template-columns: repeat({jogoAtual[0].length},auto);"
        > -->
        <table class="jogo">
        
        {#each jogoAtual as row, i}
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
</main>