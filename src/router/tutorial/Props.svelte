<style>
    p{
        width: 80%;
    }
</style>

<div class="container mt-3">
    <h3>Props</h3>
    <br>
    <p>Props adalah suatu cara untuk mengubah suatu value dalam component, value yang ada didalam component haruslah diberi export terlebih dahulu.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- Component.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{`export let nama`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>Halo nama saya {`{nama}`}<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span></pre>
    <br>

    <p>Untuk mengatur Prop akan dilakukan di pemanggilan component.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- Component.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{`export let nama`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>Halo nama saya {`{nama}`}<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
&nbsp;
<span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{`import Component from './Component.svelte'`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;Component nama<span style="color: #66cc66;">=</span><span style="color: #66cc66;">&#123;</span>udin<span style="color: #66cc66;">&#125;</span><span style="color: #66cc66;">/</span>&gt;</span></pre>
<br>

    <p>Dalam component kita juga dapat memberikan value default, dan jika tidak memberikan Prop maka yang ditampilkan adalah value default.
    Untung mengatur value default tinggal berikan saja value ke variable yang akan di export.
    </p>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- Component.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	export let nama = 'data default'
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">p</span>&gt;</span>Halo nama saya {`{nama}`}<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">p</span>&gt;</span>
&nbsp;
<span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	import Component from './Component.svelte';
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;Component <span style="color: #66cc66;">/</span>&gt;</span></pre>
<br>

    <p>Prop terdapat spread yaitu kita mengisi Prop dengan mengatur id dari Array Associative, untung menggunakan spread Prop kita harus menyamakan id dengan variable dari component.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #808080; font-style: italic;">&lt;!-- Component.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{`export let nama
	export let alamat
	export let gender
	export let github`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
	Nama 	: {`{nama}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
	Alamat 	: {`{alamat}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
	Gender 	: {`{gender}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
	Github 	: {`{github}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
&nbsp;
<span style="color: #808080; font-style: italic;">&lt;!-- App.svelte --&gt;</span>
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
	{`import Info from './Info.svelte'`}
&nbsp;
	{`let info = {
		'nama': 'Luki Himawan',
		'alamat': 'Bandung',
		'gender': 'Laki-Laki',
		'github': 'github.com/abdul'
	}`}
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">script</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;<span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
	Bido Data
<span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><span style="color: #000000; font-weight: bold;">h1</span>&gt;</span>
&nbsp;
<span style="color: #009900;">&lt;Info <span style="color: #66cc66;">&#123;</span>...info<span style="color: #66cc66;">&#125;</span> <span style="color: #66cc66;">/</span>&gt;</span></pre>
</div>