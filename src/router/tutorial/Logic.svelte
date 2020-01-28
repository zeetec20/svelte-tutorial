<script>
    let id = 1
</script>

<style>
    p{
        width: 80%;
    }

    .hidden {
        display: none;
    }
</style>

<div class="container mt-3">
    <h3>Logic</h3>
    <br>
    <p>Svelte juka memilikki operator logic yang bisa digunakaan di html, pada dasarnya html tidak memiliki operator logic tetapi dengan menggunakan Svelte anda bisa menambahkan operator logic seperti IF di html anda.</p>
    <ul>
        <li><a href=" " on:click={() => id = 1}>If Block</a></li>
        <li><a href=" " on:click={() => id = 2}>Else Block</a></li>
        <li><a href=" " on:click={() => id = 3}>Else-If Block</a></li>
        <li><a href=" " on:click={() => id = 4}>Each Block</a></li>
        <li><a href=" " on:click={() => id = 5}>Await Block</a></li>
    </ul>

    <br>
    <div class="logic1 {id != 1 ? 'hidden' : ''}">
        <h4>If Block</h4>
        <br>
        <p>If Block di svelte tidak berbeda dengan operator if di pemrogramman lain, sistem nya sama namun yang akan digunakan dalam perbandingan adalah variable yang ada di javascript.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	let click = 3
&nbsp;
	{`function buttonClick(){
		if (click != 0){
			click -= 1			
		}
	}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">button</span> on:click<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>buttonClick<span style="color: #66cc66;">&#125;</span>&gt;</span>
	Click Maksimal {`{click}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">button</span>&gt;</span>
&nbsp;
{`{#if click == 0}`}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
		anda sudah mencapai batas click	
	<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
{`{/if}`}</pre>
    </div>

    <div class="logic2 {id != 2 ? 'hidden' : ''}">
        <h4>Else Block</h4>
        <br>
        <p>Else Block adalah block yang akan dieksekusi karena perbandingan If Block yang menghasilkan nilai false.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	let click = 3
&nbsp;
	{`function buttonClick(){
		if (click != 0){
			click -= 1			
		} 
	}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">button</span> on:click<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>buttonClick<span style="color: #66cc66;">&#125;</span>&gt;</span>
	Click Maksimal {`{click}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">button</span>&gt;</span>
&nbsp;
{`{#if click == 0}`}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
		anda sudah mencapai batas click	
	<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
{`{:else}`}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
		Tombol Masih Bisa diclick	
	<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
{`{/if}`}</pre>
    </div>

    <div class="logic3 {id != 3 ? 'hidden' : ''}">
        <h4>Else-If Block</h4>
        <br>
        <p>Else If Block bisa digunakan jika If Block utama menghasilkan nilai false, namun kita ingin memberi perbandingan lagi karena tidak ingin langsung ke Else Block.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	let umur = 26;
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
	umur : {`{umur}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
&nbsp;
{`{#if umur &gt;= 46}`}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>Lansia<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
{`{:else if umur &gt;= 26}`}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>Dewasa<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
{`{:else if umur &gt;= 12}`}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>Remaja<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
{`{:else if umur &gt;= 5}`}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>Anak Anak<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
{`{:else}`}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>Balita<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
{`{/if}`}</pre>
    </div>

    <div class="logic4 {id != 4 ? 'hidden' : ''}">
        <h4>Each Block</h4>
        <br>
        <p>Each Block adalah Block yang digunakan untuk perulangan seperti For dan Foreach, variable yang dapat digunakan oleh Each Block hanya String dan Array.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{`let murid = [
		{ nama: 'Udin', nilai: 90 },
		{ nama: 'Hendru', nilai: 80 },
		{ nama: 'Lukman', nilai: 88 }
	];`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>Nilai Murid<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
{'{#each murid as mrd}'}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>{'Nama : {mrd.nama}    Nilai : {mrd.nilai}'}<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
{'{/each}'}
&nbsp;</pre>
    </div>

    <div class="logic5 {id != 5 ? 'hidden' : ''}">
        <h4>Await Block</h4>
        <br>
        <p>Await Block merupakan Block perbandingan yang digunakan untuk mendeteksi request connection, apakah masih merequest ataukan sudah siap menampilkan return, dan Await Block juga dapat mendeteksi error jika request gagal.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{'let promise = getRandomNumber();'}
&nbsp;
	{'async function getRandomNumber() {'}
		{`const res = await fetch('https://my-json-server.typicode.com/zeetec20/static-api/posts');
		const text = await res.text();`}
&nbsp;
	{	`if (res.ok) {
			return text;
		} else {
			throw new Error(text);
		}
	}`}
&nbsp;
	{`function handleClick() {
		promise = getRandomNumber();
	}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">button</span> on:click<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>handleClick<span style="color: #66cc66;">&#125;</span>&gt;</span>
	Menampilkan Post
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">button</span>&gt;</span>
&nbsp;
{`{#await promise}`}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>loading...<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
{`{:then promise}`}
	{'{#each JSON.parse(promise) as item, id}'}
		<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>{'{id + 1}. Title : {item.title}'} <span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">br</span>&gt;</span>Date : {'{item.date}'}<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;&lt;<span style="color: #000000; font-weight: bold;">br</span>&gt;</span>
	{'{/each}'}
{`{:catch error}`}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span> <span style="color: #000066;">style</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">&quot;color: red&quot;</span>&gt;</span>{'{error.message}'}<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
{`{/await}`}</pre>
    </div>
</div>