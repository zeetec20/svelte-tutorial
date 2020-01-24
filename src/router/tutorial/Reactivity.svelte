<style>
    p{
        width: 80%;
    }
</style>

<div class="container mt-3">
    <h3>Reactivity</h3>
    <br>
    <p>Reactivity adalah sebuah sistem svelte yang dimana responsive terhadap perubahan, sebagai contoh text yang selalu berubah mengikuti variable.</p>
    <pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	let count = 0;
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">button</span> on:click<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span><span style="color: #66cc66;">&#40;</span><span style="color: #66cc66;">&#41;</span> <span style="color: #66cc66;">=</span>&gt;</span> count += 1}&gt;Tambah<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">button</span>&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
	Angka {'{count}'}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span></pre>
    <p>Kita juga bisa mendeklarasi variable reactivity dengan perintah tertentu misal.</p>
    <pre class="javascript" style="font-family:monospace;">let a <span style="color: #339933;">=</span> b <span style="color: #339933;">+</span> c</pre>
    <p>Normanya jika 'b' + 'c' berubah di akhir hasil dari 'a' tidak akan berubah, namun dengan reactivity hasilnya akan berubah juga mengikuti variable yang ada di dalamnya, ini adalah contohnya.</p>
<pre class="javascript" style="font-family:monospace;"><span style="color: #339933;">&lt;!--</span> App.<span style="color: #660066;">svelte</span> <span style="color: #339933;">--&gt;</span>
<span style="color: #339933;">&lt;</span>script<span style="color: #339933;">&gt;</span>
	let count <span style="color: #339933;">=</span> <span style="color: #CC0000;">0</span><span style="color: #339933;">;</span>
&nbsp;
	$<span style="color: #339933;">:</span> kaliDua <span style="color: #339933;">=</span> count <span style="color: #339933;">*</span> <span style="color: #CC0000;">2</span>
<span style="color: #339933;">&lt;/</span>script<span style="color: #339933;">&gt;</span>
&nbsp;
<span style="color: #339933;">&lt;</span>button on<span style="color: #339933;">:</span>click<span style="color: #339933;">=</span><span style="color: #009900;">&#123;</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">=&gt;</span> count <span style="color: #339933;">+=</span> <span style="color: #CC0000;">1</span><span style="color: #009900;">&#125;</span><span style="color: #339933;">&gt;</span><span style="color: #009900;">&#123;</span>count<span style="color: #009900;">&#125;</span> <span style="color: #339933;">*</span> <span style="color: #CC0000;">2</span> <span style="color: #339933;">=</span> <span style="color: #009900;">&#123;</span>kaliDua<span style="color: #009900;">&#125;</span><span style="color: #339933;">&lt;/</span>button<span style="color: #339933;">&gt;</span></pre>
<br>

    <p>Tidak hanya variable, operator IF juga dapat digunakan dalam reactivity</p>
    <pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{`let count = 5;
	let display = false`}
&nbsp;
	{`$: if (count == 0) {
		alert('\"Hello World\"')
	}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">button</span> on:click<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span><span style="color: #66cc66;">&#40;</span><span style="color: #66cc66;">&#41;</span> <span style="color: #66cc66;">=</span>&gt;</span> count -= 1}&gt;Klick {'{count}'}x untuk menampilkan alert<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">button</span>&gt;</span>
<span style="color: #808080; font-style: italic;">&lt;!-- Akan menampilkan alert jika count bervalue 0 --&gt;</span></pre>
<br>

    <p>Jika kita berkerja dengan Array di Svelte dan melakukan perintah push terhadap suatu Array maka kita harus memberikan '=', karena di svelte reactivity dipicu oleh '=' atau assigments. </p>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- Reactivity tidak bekerja --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{`let angka = [1, 2, 3, 4];`}
&nbsp;
	{`function tambahAngka() {	
		angka.push(angka.length + 1);
	}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>angka = {`{angka}`}<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">button</span> on:click<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>tambahAngka<span style="color: #66cc66;">&#125;</span>&gt;</span>
	Tambah Angka
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">button</span>&gt;</span>
&nbsp;
<span style="color: #808080; font-style: italic;">&lt;!-- Reactivity akan bekerja --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{`let angka = [1, 2, 3, 4];`}
&nbsp;
	{`function tambahAngka() {	
		angka.push(angka.length + 1);
		angka = angka
	}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>angka = {`{angka}`}<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">button</span> on:click<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>tambahAngka<span style="color: #66cc66;">&#125;</span>&gt;</span>
	Tambah Angka
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">button</span>&gt;</span>
&nbsp;</pre>
</div>