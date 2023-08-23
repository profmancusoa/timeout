<script>
    import Panel from "../lib/panel.svelte";

    const fine_scuola = new Date("2024-06-10T12:00:00");
    const GIORNO = 86400000;//24 * 60 * 60 * 1000;
    const ORA = 3600000; //60 * 60 * 1000;
    const MINUTO = 60000; //60 * 1000;
    const SECONDO = 1000;
    let ms = 0, gg = 0, ggi = 0, hh = 0, hhi = 0, mm = 0, mmi = 0, ss = 0, ssi = 0;

    const timeout = () => {
        ms = fine_scuola - new Date();
        gg = ms / GIORNO;
        ggi = Math.trunc(gg);
        hh = ((gg - ggi) * GIORNO) / ORA;
        hhi = Math.trunc(hh);
        mm = ((hh - hhi) * ORA) / MINUTO;
        mmi = Math.trunc(mm);
        ss = ((mm - mmi) * MINUTO) / SECONDO;
        ssi = Math.ceil(ss);
    } 

    timeout();
    let clock = setInterval(timeout, 1000);
    
    function clear_clock() {
        clearInterval(clock);
    }    
</script>

<svelte:window on:beforeunload={clear_clock}/> 

<div class="wrapper">
    <h1>Quanto manca alla fine della scuola?</h1>
    <div class="counter">
        <Panel tipo="gg" num={ggi}/>
        <Panel tipo="hh" num={hhi}/>
        <Panel tipo="mm" num={mmi}/>
        <Panel tipo="ss" num={ssi}/>
    </div>
    <h2><a href="https://www.instagram.com/profmancusoa/">@profmancusoa</a></h2>
</div>

<style>
    :global(body) {
        background-image: linear-gradient(to bottom, #051937, #004d7a, #008793, #00bf72, #a8eb12);  
    }

    @media (max-width: 480px) {
        .wrapper {   
            border: 0px solid red;
            width:90%;
            height: 92vh;
            margin: auto;
            text-align: center;
            display: grid;
            grid-template-rows: 1fr 4fr 0.5fr;
            justify-items: center;
        }

        .wrapper h1 {
            border: 0px solid white;
            font-style: italic;
            font-family: 'Sniglet', cursive;
            font-size: 4.5cqh;
            letter-spacing: 0.2vw;
            color: #F9F871;
            align-self: center;
        }

        .wrapper h2 {
            align-self: flex-end;
        }

        a  {
            border: 0px solid white;
            font-size: 3cqh;
            align-self: center;
        } 

        a:link { color: #004d7a;}
        a:visited { color: #004d7a;}
        a:active { color: #004d7a;}

        .counter {
            border: 0px solid white;
            display: grid;
            grid-template-rows: repeat(4, 1fr);
            width: 35%;
            row-gap: 5cqh;
        }
    }

    @media (min-width: 481px) {
        .wrapper {   
            border: 0px solid red;
            width:90%;
            height: 98vh;
            margin: auto;
            text-align: center;
            display: grid;
            grid-template-rows: 1fr 1fr 0.7fr;
            justify-items: center;
        }

        .wrapper h1 {
            border: 0px solid white;
            font-style: italic;
            font-family: 'Sniglet', cursive;
            font-size: 5cqi;
            letter-spacing: 0.2vw;
            color: yellow;
            align-self: center;
        }

        .wrapper h2 {
            align-self: flex-end;
        }

        a  {
            border: 0px solid white;
            font-size: 3cqh;
            align-self: center;
        } 

        a:link { color: #004d7a;}
        a:visited { color: #004d7a;}
        a:active { color: #004d7a;}

        .counter {
            border: 0px solid white;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 5%;
            max-width: 100%;
            width: 90%;
        }
    }
</style>