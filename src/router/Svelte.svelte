<script>
    import {LazyLoadContainer, LazyLoad} from 'svelte-lazyload'
</script>

<style>
    p{
        width: 80%;
        margin: auto;
    }
    .title{
        color: #f06045;
        font-family: 'Overpass', sans-serif;
        font-size: 60px;
        letter-spacing: 5px;
    }

    @media (max-width: 990px){
        img{
            width: 15%;
        }
    }

    @media (max-width: 767px){
        img{
            width: 18%;
        }
    }
</style>

<div class="container mx-auto mt-3">
    <h1 class="w-100 title" style="text-align: center;">SVELTE</h1>
    <br>
    <p>Svelte adalah framework baru digunakan untuk membangun sebuah user interfase, Dimana yang melakukan sebagian besar pekerjaan mereka di browser. <br><br>

Sederhananya Svelte JS bekerja mirip dengan Framework UI seperti React & Vue yang mengupdate DOM setiap kali ada perubahan pada data/state, hanya saja program Svelte lebih fleksibel dalam penulisan kodenya dan program Svelte JS di compile menjadi vanilla js sehingga lebih cepat.
<br><br>
Saat code kita buat aplikasi maka source code akan dicompile otomatis menjadi code yang siap diupload atau digunakan oleh server / hosting.
Sehingga kita punya folder source code kemudian kita memiliki folder public sebagai run code yang siap diakses oleh user.
</p>
<br>

<p>
<LazyLoadContainer>
    <LazyLoad>
        <img src="https://drive.google.com/uc?export=view&id=1D71-YsPtX2Kl9Mdd78CcOYkkzG8G7HH8" class="rounded-circle" alt="" width="12%">
    </LazyLoad>
</LazyLoadContainer>
<b>Rich Harris</b> is a svelte maker <br>
<a target="_blank" rel="noopener" href="https://github.com/Rich-Harris">Github</a> <br>
<a target="_blank" rel="noopener" href="https://medium.com/@Rich_Harris">Medium</a></p>
</div>