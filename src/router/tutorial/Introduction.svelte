<script>
    import {LazyLoadContainer, LazyLoad} from 'svelte-lazyload'
</script>

<style>
    p{
        width: 80%;
    }
</style>

<div class="container mt-3">
    <h3>Introduction</h3>
    <br>
    <p>Setelah melakukan penginstallan langsung saja berkenalan dengan Svelte, 
    Sebenarnya susunan di svelte ini tidak beda jauh dengan html biasah.</p>
    <p>Mari kita buat project Svelte</p>

<pre class="bash" style="font-family:monospace;">npx degit sveltejs<span style="color: #000000; font-weight: bold;">/</span>template my-svelte-project
<span style="color: #7a0874; font-weight: bold;">cd</span> my-svelte-project
npm <span style="color: #c20cb9; font-weight: bold;">install</span>
&nbsp;
<span style="color: #666666; font-style: italic;">#untuk menjalankan project</span>
npm run dev</pre>

    <p>Ini adalah tampilah awal dari Svelte</p>
    <LazyLoadContainer>
        <LazyLoad>
            <img class="ml-3" style="border: solid 1px #a1a1a1;" src="https://drive.google.com/uc?export=view&id=1_VlcAHxTOON7VMoEsaNGapbwTyLdyy9a" alt="" width="70%">
        </LazyLoad>
    </LazyLoadContainer>
    <br>
    <p>Setelah projectnya sudah di install mari kita intip isinya.</p>
    <LazyLoadContainer>
        <LazyLoad>
            <img class="ml-3" src="https://drive.google.com/uc?export=view&id=18maxIwsJj84qDhBXWg7w9gZOBJ6Zez6W" alt="" width="20%">
        </LazyLoad>
    </LazyLoadContainer>
    <br>
    <br>
    <p>Mari buka folder src dan lihat isinya.</p>
    <LazyLoadContainer>
        <LazyLoad>
            <img class="ml-3" src="https://drive.google.com/uc?export=view&id=1x8gpz8EyWwqfHueg3SXgEATNTw4xXM-C" alt="" width="20%">
        </LazyLoad>
    </LazyLoadContainer>
    <br>
    <br>
    <p>Didalam sana terdapat App.svelte dan main.js, file App merupakan tempat diamana kita akan menulis program, misal kita akan menampilkan text "Hello World!" di project kita cukup dengan menuliskan seperti html.</p>
<pre class="html4strict" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>Hello World!<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span></pre>

    <p>Sekarang mari kita coba tambahkan data.</p>
<pre class="html4strict" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	let name = 'Programmer';
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>Hello {'{world}'} Banyuwangi<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
&nbsp;
<span style="color: #808080; font-style: italic;">&lt;!-- Result --&gt;</span>
<span style="color: #808080; font-style: italic;">&lt;!-- Hello Programmer Banyuwangi --&gt;</span></pre>

    <p>Kita juga bisa menentukan atribut dari tag html melalui variable, dan untuk penulisan javascript dan css menggunakan tag 'script' dan 'style'.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	let blue = 'blue';
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span> <span style="color: #000066;">class</span><span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>blue<span style="color: #66cc66;">&#125;</span>&gt;</span>Hello Guys<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">style</span>&gt;</span>
	.blue{`{
		color: blue;
	}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">style</span>&gt;</span></pre>

    <p>Kita juga bisa membuat component, intinya kita akan memecah bagian-bagian dari program kita. Kita akan membuat file baru Text.svelte yang berisi tag 'p' dan coba lihat hasilnya, nanti akan menampilkan text dari tag 'h1' file App.svelte kemudian dibawahnya ada juga text dari file Text.svelte.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	import Text from './Text.svelte'
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>Svelte<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">Text</span> <span style="color: #66cc66;">/</span>&gt;</span>
&nbsp;
&nbsp;
<span style="color: #808080; font-style: italic;">&lt;!--Text.svelte--&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>Halo saya svelte<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
&nbsp;
&nbsp;
<span style="color: #808080; font-style: italic;">&lt;!-- result --&gt;</span>
<span style="color: #808080; font-style: italic;">&lt;!-- Svelte --&gt;</span>
<span style="color: #808080; font-style: italic;">&lt;!-- Halo saya svelte --&gt;</span></pre>
</div>