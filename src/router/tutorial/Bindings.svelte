<style>
    p{
        width: 80%;
    }
</style>

<div class="container mt-3">
    <h3>Bindings</h3>
    <br>
    <p>Binding artinya adalah mengikat, didalam Svelte binding digunakan untuk mengikat variable pada tag input. Variable maupun tag input yang terkena binding value mereka akan berubah mengikut perubahan satu sama lain.</p>

<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	let text2 = 'World';
	let text1 = 'Hello' 
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">input</span> <span style="color: #000066;">value</span><span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>`$<span style="color: #66cc66;">&#123;</span>text1<span style="color: #66cc66;">&#125;</span> $<span style="color: #66cc66;">&#123;</span>text2<span style="color: #66cc66;">&#125;</span>`<span style="color: #66cc66;">&#125;</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">input</span> bind:<span style="color: #000066;">value</span><span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>text2<span style="color: #66cc66;">&#125;</span>&gt;</span></pre>
    <br>
    
    <p>Sekarang kita coba untuk implementasi binding menggunakan checkbox untuk menampilkan text dan menutup text. Binding di checkbox biasahnya ditaruh dalam parameter checked karena yang berubah saat kita berinteraksi dengan checkbox hanyalah parameter checked.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	let show = false;
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">label</span> <span style="color: #000066;">for</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">&quot;checkbox&quot;</span>&gt;</span>{'{!show ? "Buka" : "Tutup"}'} Text<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">label</span>&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">input</span> <span style="color: #000066;">id</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">&quot;checkbox&quot;</span> <span style="color: #000066;">type</span><span style="color: #66cc66;">=</span>checkbox bind:<span style="color: #000066;">checked</span><span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>show<span style="color: #66cc66;">&#125;</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span> <span style="color: #000066;">style</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">&quot;display: {"{!show ? 'none' : 'block'}"}&quot;</span>&gt;</span>
	Hello World
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span></pre>
    <br>

    <p>Dalam binding terdapat binding group yang dikususkan untuk input type radio dan checkbox, cara kerja binding group adalah ketika kita menginputkan melalui input radio / checkbox maka akan diteruskan ke variable yang ditentukan.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	let selectGender
	let gender = ['perempuan', 'laki-laki']
&nbsp;
	let selectHobby = []
	let hobby = ['Membaca Buku', 'Bermain Game', 'Sepak Bola']
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
&nbsp;
{'{#each gender as gdr}'}
	{'{gdr}'}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">li</span>&gt;&lt;<span style="color: #000000; font-weight: bold;">input</span> <span style="color: #000066;">type</span><span style="color: #66cc66;">=</span>radio bind:group<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>selectGender<span style="color: #66cc66;">&#125;</span> <span style="color: #000066;">value</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">&quot;{'{gdr}'}&quot;</span>&gt;&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">li</span>&gt;</span>
{'{/each}'}
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h6</span>&gt;</span>
	{'{typeof selectGender == "undefined" ? "Pilih Gender" : selectGender }'}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h6</span>&gt;</span>
&nbsp;
{'{#each hobby as hby}'}
	{'{hby}'}
	<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">li</span>&gt;&lt;<span style="color: #000000; font-weight: bold;">input</span> <span style="color: #000066;">type</span><span style="color: #66cc66;">=</span>checkbox bind:group<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>selectHobby<span style="color: #66cc66;">&#125;</span> <span style="color: #000066;">value</span><span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>hby<span style="color: #66cc66;">&#125;</span>&gt;&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">li</span>&gt;</span>
{'{/each}'}
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h6</span>&gt;</span>
	{'{selectHobby}'}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h6</span>&gt;</span></pre>
    <br>

    <p></p>
</div>