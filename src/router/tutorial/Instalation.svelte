<script>
    let node = true
    let npm = false
    let svelte = false
</script>

<div class="container mt-3">
    <h3>Instalation</h3>
    <br>
    <p>Sebelum mepelajari svelte kita terlebih dahulu mempersiapkan software yang perlu kita install</p>
    <ol>
        <li><a href=" " style="cursor: pointer;" on:click={() => {node = true, npm = false, svelte = false}}>Node.Js</a></li>
        <li><a href=" " style="cursor: pointer;" on:click={() => {node = false, npm = true, svelte = false}}>NPM</a></li>
        <li><a href=" " style="cursor: pointer;" on:click={() => {node = false, npm = false, svelte = true}}>Svelte</a></li>
    </ol>

    <div class="instalation mt-5">
        <div class={'node', node == false ? 'none' : ''}>
            <h4>Node.Js</h4>
            <p>
            Node.Js adalah bahasa server side yang berasal dari javascript, dalam membangun website menggunakan svelte kita membutuhkan Node.Js.
            Dalam Node.Js terdapat NPM (Node Package Manager) yaitu managemen paket libari untuk Node.Js, dengan NPM kita dapat memanagemen librari yang kita butuhkan.
            </p>
            <br>
            <h5>Windows</h5>
            <p>Untuk instalation di Windows cukup mengunduh installer yang telah disediakan oleh Node.Js. Silahkan buka halaman <a href="https://nodejs.org/en/download/" target="_blank" rel="noopener noreferrer">download Node.Js</a> 
            dan download Node.Js untuk windows. Setelah Selesai mendownload Node.Js lakukan instaltion Node.Js sesuai panduan.
            </p>
            <br>
            <h5>Linux</h5>
            <p>Instalation di Linux sedikit berbeda dengan Windows
            Silahkan bukan terminal dan jalankan peritah tersebut, pilihlah Node.Js sesuai kebutuhan anda.</p>

<pre class="bash" style="font-family:monospace;">
<span style="color: #666666; font-style: italic;">#Node.js v13.x:</span>
&nbsp;
<span style="color: #666666; font-style: italic;"># Using Ubuntu</span>
curl <span style="color: #660033;">-sL</span> https:<span style="color: #000000; font-weight: bold;">//</span>deb.nodesource.com<span style="color: #000000; font-weight: bold;">/</span>setup_13.x <span style="color: #000000; font-weight: bold;">|</span> <span style="color: #c20cb9; font-weight: bold;">sudo</span> <span style="color: #660033;">-E</span> <span style="color: #c20cb9; font-weight: bold;">bash</span> -
<span style="color: #c20cb9; font-weight: bold;">sudo</span> <span style="color: #c20cb9; font-weight: bold;">apt-get install</span> <span style="color: #660033;">-y</span> nodejs
&nbsp;
<span style="color: #666666; font-style: italic;"># Using Debian, as root</span>
curl <span style="color: #660033;">-sL</span> https:<span style="color: #000000; font-weight: bold;">//</span>deb.nodesource.com<span style="color: #000000; font-weight: bold;">/</span>setup_13.x <span style="color: #000000; font-weight: bold;">|</span> <span style="color: #c20cb9; font-weight: bold;">bash</span> -
<span style="color: #c20cb9; font-weight: bold;">apt-get install</span> <span style="color: #660033;">-y</span> nodejs
&nbsp;
&nbsp;
<span style="color: #666666; font-style: italic;">#Node.js v12.x: </span>
<span style="color: #666666; font-style: italic;">#LTS (Long Term Support) </span>
&nbsp;
<span style="color: #666666; font-style: italic;"># Using Ubuntu</span>
curl <span style="color: #660033;">-sL</span> https:<span style="color: #000000; font-weight: bold;">//</span>deb.nodesource.com<span style="color: #000000; font-weight: bold;">/</span>setup_12.x <span style="color: #000000; font-weight: bold;">|</span> <span style="color: #c20cb9; font-weight: bold;">sudo</span> <span style="color: #660033;">-E</span> <span style="color: #c20cb9; font-weight: bold;">bash</span> -
<span style="color: #c20cb9; font-weight: bold;">sudo</span> <span style="color: #c20cb9; font-weight: bold;">apt-get install</span> <span style="color: #660033;">-y</span> nodejs
&nbsp;
<span style="color: #666666; font-style: italic;"># Using Debian, as root</span>
curl <span style="color: #660033;">-sL</span> https:<span style="color: #000000; font-weight: bold;">//</span>deb.nodesource.com<span style="color: #000000; font-weight: bold;">/</span>setup_12.x <span style="color: #000000; font-weight: bold;">|</span> <span style="color: #c20cb9; font-weight: bold;">bash</span> -
<span style="color: #c20cb9; font-weight: bold;">apt-get install</span> <span style="color: #660033;">-y</span> nodejs
</pre>

        </div>
        
        <div class={'npm', npm == false ? 'none' : ''}>
            <h4>NPM</h4>
            <p>
            NPM (Node Package Manager) seperti yang saya bilang tadi, NPM digunakan untuk memanajemen librari yang dibutuhkan.
            Sebenarnya saat installasi Node.Js, NPM akan ikut terinsatall, namun meski  sudah terinstall NPM perlu diperbarui, cukup dengan mengeksekusi perintah dibwah NPM akan diperbarui.
            </p>

<pre class="bash" style="font-family:monospace;">npm <span style="color: #c20cb9; font-weight: bold;">install</span> npm<span style="color: #000000; font-weight: bold;">@</span>latest <span style="color: #660033;">-g</span></pre>
        </div>

        <div class={'svelte', svelte == false ? 'none' : ''}>
            <h4>Svelte</h4>
            <p>
            Node.Js dan NPM sudah terinstall sekarang tinggal menginstall Svelte, untuk menginstall kita akan menggunakan NPM.
            dan NPM menyediakan 2 cara untuk install librari atau framework, untuk perintah installasi bisa dilihat dibawah.
            </p>

<pre class="bash" style="font-family:monospace;">npm init
npm <span style="color: #c20cb9; font-weight: bold;">install</span> svelte</pre>

        </div>
    </div>
</div>

<style>
    .none{
        display: none;
    }

    .instalation p{
        width: 80%;
    }
</style>