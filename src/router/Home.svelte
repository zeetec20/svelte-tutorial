<script>
    import {LazyLoadContainer, LazyLoad} from 'svelte-lazyload'
    import Card from '../component/Card.svelte'

    let card = [
        {
            'title': 'Apa itu svelte ?',
            'text': 'Singkatnya Svelte Adalah sebuah Framework untuk membuat website.',
            'button': 'Cari Tahu',
            'url': '/svelte'
        },
        {
            'title': 'Cara menggunakan svelte ?',
            'text': 'Svelte adalah framewrok yang berdiri sendiri, yang dimana kita menulis di file App.svelte.',
            'button': 'Belajar',
            'url': '/tutorial'
        }
    ]
</script>

<div class="container overflow-auto m-auto">
    <div class="row wrap-title">
        <h1 class="col-lg-12 title w-100 m-auto" style="text-align: center;">Ngulik SVELTE</h1>
    </div>

    <div class="row">
        <div class="col-lg-12 frame">
            <LazyLoadContainer>
                <LazyLoad>
                    <img src="https://drive.google.com/uc?export=view&id=1guNT4-EdBlJhIFdBVqZ2EQcFhj3vKkJ0" alt="">
                </LazyLoad>
            </LazyLoadContainer>
        </div>
    </div>

    <div class="row listCard">
        {#each card as crd}
            <Card card={crd}></Card>
        {/each}
    </div>
</div>

<style>
    .wrap-title{
        position: absolute;
        left: 0;
        right: 0;
        margin-top: 7%;
        z-index: 2;
    }

    .title{
        position: absolute;
        /* left: 0; */
        right: 0;
        text-align: center;
        color: tomato;
        font-family: 'Overpass', sans-serif;
        font-size: 60px;
        letter-spacing: 5px;
        text-decoration: #429f95 underline;
        width: 100%;
    }

    .frame{
        position: absolute;
        padding-top: 10px;
        width: 40%;
        margin: auto;
        overflow: hidden;
        left: 0;
        right: 0;
        z-index: 0;
        /* background-color: aqua; */
    }

    img{
        margin: auto;
        width: 100%;
        left: 0;
        right: 0;
        /* background-color: blue; */
    }

    .listCard{
        margin: auto;
        margin-top: 25%;
    }

    @media(max-width: 520px){
        .listCard{
            margin-top: 55%;
        }
    }
</style>