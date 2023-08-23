<script>
    export let num = 0;
    export let tipo;
    
    let tipo2txt = {
        gg: 'Giorni',
        hh: 'Ore',
        mm: 'Minuti',
        ss: 'Secondi'
    }
</script>

<div class="panel">
    <div class="number">{num}</div>
    <div class="title">{tipo2txt[tipo]}</div>
</div>

<style>

@media (max-width: 480px) {
    .panel {
            border: 2px solid white;
            border-radius: 15px;
            width: 100%;
            display: grid;
            grid-template-rows: 2fr 1fr;
            min-width: 0px;
            justify-content: center;
            align-content: center;
            box-shadow: 15px 15px 15px 0px rgba(255,255,255,0.1);
        }

        .number {
            border: 0px solid yellow;
            font-family: 'Black Ops One', cursive;
            font-size: 12cqw;
            letter-spacing: 0.2cqw;
            color: #F9F871;
            text-shadow: 4px 4px 10px #051937;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .title {
            border: 0px solid yellow;
            font-family: 'Sniglet', cursive;
            color: white;
            font-size: 5cqw;
            display: flex;
            align-items:start;
            justify-content: center;
            font-weight: bold;
        }
    }

    @media (min-width: 481px) {
        .panel {
            border: 2px solid white;
            border-radius: 15px;
            width: 100%;
            display: grid;
            grid-template-rows: 2fr 1fr;
            min-width: 0px;
            justify-content: center;
            align-content: center;
            box-shadow: 15px 15px 15px 0px rgba(255,255,255,0.1);
        }

        .number {
            border: 0px solid yellow;
            font-family: 'Black Ops One', cursive;
            font-size: 7cqi;
            letter-spacing: 0.2cqw;
            color: yellow;
            text-shadow: 4px 4px 10px #051937;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .title {
            border: 0px solid yellow;
            font-family: 'Sniglet', cursive;
            color: white;
            font-size: 3cqw;
            display: flex;
            align-items:start;
            justify-content: center;
            font-weight: bold;
        }
    }
</style>