<style>
    p{
        width: 80%;
    }
</style>

<div class="container mt-3">
    <h3>Routing</h3>
    <br>
    <p>Svelte sebenarnya tidak menyediakan routing maka kita memerlukan pihak ketiga yaitu library yang bernama <b>Page</b>, untuk menggunakan Page kita perlu mengistall menggunakan npm.</p>
<pre class="bash" style="font-family:monospace;">npm <span style="color: #c20cb9; font-weight: bold;">install</span> page</pre>
    <br>

    <p>Setelah selesai mengistall Page langsung menuju file package.json, di package.json line 7 ada yang harus diubah, silahkan ubah seperti dibawah.</p>
<pre class="javascript" style="font-family:monospace;"><span style="color: #3366CC;">&quot;start&quot;</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">&quot;sirv public --single&quot;</span></pre>
    <br>

    <p>Sekarang tinggal membuat router, buat folder router di folder src dengan didalamnya file Home.svelte tuliskan tag 'h1' di dalam Home.svelte, setelah itu buka App.svelte isikan script seperti dibawah.</p>
<pre class="javascript" style="font-family:monospace;"><span style="color: #339933;">&lt;</span>script<span style="color: #339933;">&gt;</span>
  <span style="color: #006600; font-style: italic;">// App.svelte</span>
&nbsp;
  <span style="color: #FF0000;">import</span> router from <span style="color: #3366CC;">&quot;page&quot;</span>
&nbsp;
  <span style="color: #FF0000;">import</span> Home from <span style="color: #3366CC;">'./routes/Home.svelte'</span>
<span style="color: #339933;">&lt;/</span>script<span style="color: #339933;">&gt;</span></pre>
    <p>Pertama kita importkan library Page dan component Home.</p>
    <br>

    <p>Setelah Page dan Home sudah di import mari kita atur routernya, pertama kita bikin router dengan url '/' disikan di parameter pertama ini menandakan halaman yang pertama kali ditampilkan, 
    Untuk parameter kedua kita isi dengan function yang mengassaignment page dengan component Home.
    </p>
<pre class="javascript" style="font-family:monospace;"><span style="color: #339933;">&lt;</span>script<span style="color: #339933;">&gt;</span>
  <span style="color: #006600; font-style: italic;">// App.svelte</span>
&nbsp;
  <span style="color: #FF0000;">import</span> router from <span style="color: #3366CC;">&quot;page&quot;</span>
  <span style="color: #FF0000;">import</span> Home from <span style="color: #3366CC;">'./routes/Home.svelte'</span>
&nbsp;
  let page  
&nbsp;
  router<span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'/'</span><span style="color: #339933;">,</span> <span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">=&gt;</span> page <span style="color: #339933;">=</span> Home<span style="color: #009900;">&#41;</span>
  router.<span style="color: #660066;">start</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span>
<span style="color: #339933;">&lt;/</span>script<span style="color: #339933;">&gt;</span></pre>
    <br>

    <p>Svelte memiliki special element svelte:component. Element ini akan kita tambahkan ke App.svelte fungsi dari element ini adalah menampilkan page yang valuenya adalah Component karena sudah diubah oleh router. svelte:component sebenarnya sama saja seperti menampilkan Component secara normal, tapi karena element ini mebutuhkan variable atau component untuk ditampilkan, jadi bisa fleksibel diubah ubah valuenya dengan router.</p>
<pre class="html5" style="font-family:monospace;"><span style="color: #009900;">&lt;svelte:component&gt;</span></pre>
    <p>Sekarang tinggal kita implementasikan ke project kita seperti dibawah.</p>
<pre class="javascript" style="font-family:monospace;"><span style="color: #339933;">&lt;</span>script<span style="color: #339933;">&gt;</span>
  <span style="color: #006600; font-style: italic;">// App.svelte</span>
&nbsp;
  <span style="color: #FF0000;">import</span> router from <span style="color: #3366CC;">&quot;page&quot;</span>
  <span style="color: #FF0000;">import</span> Home from <span style="color: #3366CC;">'./routes/Home.svelte'</span>
&nbsp;
  let page  
&nbsp;
  router<span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'/'</span><span style="color: #339933;">,</span> <span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">=&gt;</span> page <span style="color: #339933;">=</span> Home<span style="color: #009900;">&#41;</span>
  router.<span style="color: #660066;">start</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span>
<span style="color: #339933;">&lt;/</span>script<span style="color: #339933;">&gt;</span>
&nbsp;
<span style="color: #339933;">&lt;</span>svelte<span style="color: #339933;">:</span>component <span style="color: #000066; font-weight: bold;">this</span><span style="color: #339933;">=</span><span style="color: #009900;">&#123;</span>page<span style="color: #009900;">&#125;</span> <span style="color: #339933;">/&gt;</span></pre>
    <br>

    <p>Coba kita lihat hasilnya, maka akan menampilkan isi dari Home.app, sekarang kita coba lagi buat halaman kedua dan menambahkan text diatas element svelte:component.</p>
<pre class="javascript" style="font-family:monospace;"><span style="color: #339933;">&lt;</span>script<span style="color: #339933;">&gt;</span>
  <span style="color: #006600; font-style: italic;">// App.svelte</span>
&nbsp;
  <span style="color: #FF0000;">import</span> router from <span style="color: #3366CC;">&quot;page&quot;</span>
  <span style="color: #FF0000;">import</span> Home from <span style="color: #3366CC;">'./routes/Home.svelte'</span>
  <span style="color: #FF0000;">import</span> About from <span style="color: #3366CC;">'./router/About.svelte'</span>
&nbsp;
  let page  
&nbsp;
  router<span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'/'</span><span style="color: #339933;">,</span> <span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">=&gt;</span> page <span style="color: #339933;">=</span> Home<span style="color: #009900;">&#41;</span>
  router<span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'/about'</span><span style="color: #339933;">,</span> <span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">=&gt;</span> page <span style="color: #339933;">=</span> About<span style="color: #009900;">&#41;</span>
  router.<span style="color: #660066;">start</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span>
<span style="color: #339933;">&lt;/</span>script<span style="color: #339933;">&gt;</span>
&nbsp;
<span style="color: #339933;">&lt;</span>svelte<span style="color: #339933;">:</span>component <span style="color: #000066; font-weight: bold;">this</span><span style="color: #339933;">=</span><span style="color: #009900;">&#123;</span>page<span style="color: #009900;">&#125;</span> <span style="color: #339933;">/&gt;</span></pre>
    <br>

    <p>Dengan Page kita juga bisa mengatur halaman 404 not found</p>
<pre class="javascript" style="font-family:monospace;"><span style="color: #339933;">&lt;</span>script<span style="color: #339933;">&gt;</span>
  <span style="color: #006600; font-style: italic;">// App.svelte</span>
&nbsp;
  <span style="color: #FF0000;">import</span> router from <span style="color: #3366CC;">&quot;page&quot;</span>
  <span style="color: #FF0000;">import</span> Home from <span style="color: #3366CC;">'./routes/Home.svelte'</span>
  <span style="color: #FF0000;">import</span> About from <span style="color: #3366CC;">'./router/About.svelte'</span>
  <span style="color: #FF0000;">import</span> NotFound <span style="color: #3366CC;">'./router/NotFound.svelte'</span>
&nbsp;
  let page  
&nbsp;
  router<span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'/'</span><span style="color: #339933;">,</span> <span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">=&gt;</span> page <span style="color: #339933;">=</span> Home<span style="color: #009900;">&#41;</span>
  router<span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'/about'</span><span style="color: #339933;">,</span> <span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">=&gt;</span> page <span style="color: #339933;">=</span> About<span style="color: #009900;">&#41;</span>
  router<span style="color: #009900;">&#40;</span><span style="color: #3366CC;">'*'</span><span style="color: #339933;">,</span> <span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">=&gt;</span> page <span style="color: #339933;">=</span> NotFound<span style="color: #009900;">&#41;</span>
  router.<span style="color: #660066;">start</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span>
<span style="color: #339933;">&lt;/</span>script<span style="color: #339933;">&gt;</span>
&nbsp;
<span style="color: #339933;">&lt;</span>svelte<span style="color: #339933;">:</span>component <span style="color: #000066; font-weight: bold;">this</span><span style="color: #339933;">=</span><span style="color: #009900;">&#123;</span>page<span style="color: #009900;">&#125;</span> <span style="color: #339933;">/&gt;</span></pre>
</div>