<script>
    import {LazyLoadContainer, LazyLoad} from 'svelte-lazyload'

    export let brandUrl
    export let site
    export let menu
</script>

<nav class="navbar navbar-expand-lg navbar-light w-100 mw-100 col-lg-12" style="background-color: #429f95;">
	<div class="container">
        <a class="navbar-brand navbar-brand-image" href="{brandUrl}">
            <LazyLoadContainer>
                <LazyLoad>
                    <img src="https://drive.google.com/uc?export=view&id=1B9IkCjBjsGMlxLCthAlQco4id3-N56vM" width="30" height="30" class="d-inline-block align-top rounded-circle" alt="">
                </LazyLoad>
            </LazyLoadContainer>
        </a>
        <a class="navbar-brand navbar-brand-text text-light" href="{brandUrl}">{site}</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        {#if typeof menu != 'undefined'}
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ml-auto">
                    {#each menu as m, id}
                        {#if id <= 2}
                            <li class="nav-item active">
                                <a class="nav-link text-light" href={m.url == '/tutorial' ? '/tutorial' : m.url}>{m.name}<span class="sr-only">(current)</span></a>
                            </li>
                        {/if}
                    {/each}
                </ul>
            </div>
        {/if}
    </div>
</nav>

<style>
    .navbar{
        font-family: 'Roboto', sans-serif;
        font-weight: 500;
        box-shadow: 0px 7px 10px -10px #00000098;
        position: absolute;
        z-index: 6;
        left: 0;
        right: 0;
        top: 0;
        height: 9%;
        min-height: 50px;
        max-height: 70px !important;
        padding: 0 !important;
    }
    
    .navbar-collapse{
        background-color: #429f95;
    }
    
    .navbar .navbar-brand-image{
        padding-left: 8px;
    }
    
    .navbar .nav-link:focus{
        color: #f8f7fa !important;
    }

    .navbar button{
        outline: none !important;
    }

    @media (max-width: 995px){
        .navbar-collapse .nav-link{
            margin-left: 10px !important;
        }
    }

    @media (max-width: 420px){
        .navbar-brand-text{
            font-size: 12px
        }
    }

    @media (max-width: 325px){
        .navbar-brand-image{
            width: 20px;
        }

        .navbar-collapse a{
            font-size: 12px;
        }
    }
</style>