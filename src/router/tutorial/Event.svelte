<style>
    p{
        width: 80%;
    }
</style>

<div class="container mt-3">
    <h3>Event</h3>
    <br>
    <p>Svelte juga memiliki event sendiri yang sudah disediakan di beberapa tag html.</p>
    <p>Contoh Event di Svelte.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">button</span> on:click<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span><span style="color: #66cc66;">&#40;</span><span style="color: #66cc66;">&#41;</span> <span style="color: #66cc66;">=</span>&gt;</span> alert('click')}&gt;
	click me
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">button</span>&gt;</span></pre>

    <p>Button akan menampilkan alert jika kita tekan.</p>
    <br>

    <p>Event Modifier juga terdapat di svelte, yaitu kita bisa memodifikasi event dengan beberapa pilihan</p>
    <ol>
        <li>PreventDefault<br>
        PreventDefault adalah Event Modifier yang menghilangkan sifat aslinya, misal tag 'a' di html jika di click akan menriderect, namun jika kita tambahkan Event Modifier PreventDefault pada Event tag 'a' tidak akan meriderect.
        </li>
        <li>StopPagination</li>
        <li>Passive</li>
        <li>Capture</li>
        <li>Once<br>
        Once adalah Event Modifier yang membuat Event hanya mengesekusi perintah satu kali.
        </li>
    </ol>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">button</span> on:click|once<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span><span style="color: #66cc66;">&#40;</span><span style="color: #66cc66;">&#41;</span> <span style="color: #66cc66;">=</span>&gt;</span> console.log('hanya sekali')}&gt;
	Click
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">button</span>&gt;</span> 
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">a</span> <span style="color: #000066;">href</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">&quot;/&quot;</span> on:click|preventDefault&gt;</span>Tag A yang tidak bisa riderict<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">a</span>&gt;</span></pre>
    <br>

    <p>Svelte juga menyediakan fungsi <u>createEventDispatcher</u> fungsi ini berguna untuk membuat custom event.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{'import Inner from "./Angka.svelte";'}
&nbsp;
	{`function pesan(event) {
		alert(event.detail.pesan);
	}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;Angka on:angkahabis<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>pesan<span style="color: #66cc66;">&#125;</span>&gt;&lt;<span style="color: #66cc66;">/</span>Angka&gt;</span>
&nbsp;
<span style="color: #808080; font-style: italic;">&lt;!-- Angka.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{`import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();
	let angka = 5`}
&nbsp;
	{`$: if (angka == 0) {
		dispatch('angkahabis', {
			pesan: 'angka habis'
		})
	}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">button</span> on:click<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span><span style="color: #66cc66;">&#40;</span><span style="color: #66cc66;">&#41;</span> <span style="color: #66cc66;">=</span>&gt;</span> angka != 0 ? angka -= 1 : ''}&gt;
	{'Kurangi Angka {angka} dengan 1'}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">button</span>&gt;</span></pre>
    <p>Cara kerja createEventDispatcher yaitu, component yang dimport mengirimkan event dan diterima oleh App, agar bisa diterima nama event harus sama dengan pengirim, nama event ditentukan di parameter pertama untuk parameter ke dua kita bisa mengisikan 
    object dan ditampilkan di App.</p>
<br>

    <p>Event di svelte juga memiliki sifat forwarnding, namun itu berlaku jika Event tidak diisikan fungsi</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{'import Component from "./Component.svelte";'}
&nbsp;
	{`function showAlert(event) {
		alert('tombol telah diclick');
	}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;Component on:click<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>showAlert<span style="color: #66cc66;">&#125;</span><span style="color: #66cc66;">/</span>&gt;</span>
&nbsp;
<span style="color: #808080; font-style: italic;">&lt;!-- Component.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">button</span> on:click&gt;</span>
	Click
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">button</span>&gt;</span></pre>
</div>