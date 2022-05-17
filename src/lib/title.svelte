<script>
    export let title = "Geoffrey Maddock's Site"
    export let width = 100
    export let height = 100
</script>
<div class="title">
    <img src="/basic-logo.svg" alt="Geoff Maddock site logo" width={width} height={height}>
    <span>
        <h1>{title}</h1>
        <h2>PROGRAMMER, DESIGNER, PROMOTER, DJ</h2>
    </span>
</div>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Arvo:wght@400;700&display=swap');
    .title {
        display: flex;
    }

    .title img {
        display: inline-block;
        filter: invert(88%) sepia(18%) saturate(886%) hue-rotate(199deg) brightness(100%) contrast(90%) drop-shadow(0 0 0.75rem crimson);  
    }
    .title h1 {
        margin-left: 10px;
        font-family: 'Arvo', serif;
        font-weight: 700;
        text-align: left;
        margin-bottom: 0px;
        margin-top: 15px;
    }

    .title h2 {
        margin-left: 10px;
        font-family: 'Arvo', serif;
        font-weight: 700;
        text-align: left;
        margin-top: 0px;
    }
    
</style>