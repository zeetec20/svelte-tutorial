<script>
    export let card
</script>

{#if typeof card != 'undefined'}
    <div class="col-lg-6 mx-auto">
        <div class="card">
            <div class="card-body">
                <h5 class="card-title">{card.title}</h5>
                <p class="card-text">{card.text}</p>
                <a href="{card.url}" class="btn btn-primary text-light">{card.button}</a>
            </div>
        </div> 
    </div>   
{/if}

<style>
    .card{
        margin: auto;
        margin-bottom: 10px;
        border-color: #429f95;
        background-color: #ffc6bc;
        font-family: 'Overpass', sans-serif;
    }

    .card .card-title{
        width: 100%;
        padding-bottom: 12px;
        border-bottom: solid #429f95 1px;
    }

    .card .btn{
        background-color: #429f95 !important;
        border: none;
    }
</style>