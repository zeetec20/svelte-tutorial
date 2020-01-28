<script>
    import {LazyLoadContainer, LazyLoad} from 'svelte-lazyload'
</script>

<style>
    p{
        width: 80%;
    }
</style>

<div class="container mt-3">
    <h3>Deploy</h3>
    <br>
    <p>Setelah kita sudah selesai membuat website tentu saja kita ingin mendeploynya agar bisa dilihat oleh orang lain. Untuk mendeploy Svelte 
    kita bisa menggunakan <a target="_blank" rel="noopener" href="https://www.netlify.com/">Netlify</a>, caranya pun cukup mudah. Pertama login atau register terlebih dahulu untuk menggunakan netifly bisa dengan GitHub, GitLab, BitBucket dan Email. Silahkan menuju halaman site dan disitu ada tempat untuk drag drop, kalian bisa mendrop folder public dari project Svelte disitu.</p>
    <LazyLoadContainer>
        <LazyLoad>
            <img src="https://drive.google.com/uc?export=view&id=1FcfKWFNdNcb48q8XW1i40c-VH6cervEE" alt="" class="ml-3">
        </LazyLoad>
    </LazyLoadContainer>
    <br>
    <LazyLoadContainer>
        <LazyLoad>
            <img src="https://drive.google.com/uc?export=view&id=1HC6lVJ5jPGd5h77tB9ABZh8J-YHIUYOk" alt="" width="70%" class="ml-3">
        </LazyLoad>
    </LazyLoadContainer>
    <br>
    <p>Setelah anda mendrop folder public maka netlify akan langsung memproses project kamu menjadi website, awalnya addressnya akan kacau namun ketika netlify sudah selesai memproses anda bisa menganti address website anda.</p>
    <LazyLoadContainer>
        <LazyLoad>
            <img src="https://drive.google.com/uc?export=view&id=1ragFqoggyr4l9g7OhcOhMsnL3oQyAu0S" alt="" width="70%" class="ml-3">
        </LazyLoad>
    </LazyLoadContainer>
</div>