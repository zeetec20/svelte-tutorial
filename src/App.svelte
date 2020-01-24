<svelte:head>
	<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

	<title>{site} | {title}</title>

	<link href="https://fonts.googleapis.com/css?family=Overpass|Roboto&display=swap" rel="stylesheet">
	<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
</svelte:head>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		overflow-x: hidden;
		/* overflow-y: hidden; */
	}

	@media (max-width: 995px) {
		:global(body) {
			overflow-y: visible;
		}
	}
</style>

<script>
	import "popper.js/dist/popper.min.js"
	import "jquery/dist/jquery.js"
	import "bootstrap/dist/js/bootstrap.min.js"
	import router from 'page'

	let site = 'Komunitas Programmer Banyuwangi'

	let title = 'Home'
	let body
	let params
	let place
	let next
	let previous
	let blur = 50
	let tutorial = false
	let navPosition = 'absolute'
	let navMarginTop = '10%'

	import Home from './router/Home.svelte'
	import Tutorial from './router/Tutorial.svelte'
	import Svelte from './router/Svelte.svelte'
	import NotFound from './router/404.svelte'

	import T_Instalation from  './router/tutorial/Instalation.svelte'
	import T_Introduction from './router/tutorial/Introduction.svelte'
	import T_Reactivity from './router/tutorial/Reactivity.svelte'
	import T_Props from './router/tutorial/Props.svelte'
	import T_Logic from './router/tutorial/Logic.svelte'
	import T_Event from './router/tutorial/Event.svelte'
	import T_Bindings from './router/tutorial/Bindings.svelte'
	import T_Routing from './router/tutorial/Routing.svelte'
	import T_Deploy from './router/tutorial/Deploy.svelte'

	import Navbar from './component/Navbar.svelte'

	let menu = [
		{
			'name': 'Home',
			'url': '/',
			'com': Home
		},
		{
			'name': 'Svelte',
			'url': '/svelte',
			'com': Svelte
		},
		{
			'name': 'Tutorial',
			'url': '/tutorial',
		},
		{
			'name': 'Instalation',
			'url': '/tutorial/instalation',
			'com': T_Instalation
		},
		{
			'name': 'Introduction',
			'url': '/tutorial/introduction',
			'com': T_Introduction
        },
        {
            'name': 'Ractivity',
			'url': '/tutorial/reactivity',
			'com': T_Reactivity
        },
        {
            'name': 'Props',
			'url': '/tutorial/props',
			'com': T_Props
        },
        {
            'name': 'Logic',
			'url': '/tutorial/logic',
			'com': T_Logic
        },
        {
            'name': 'Event',
			'url': '/tutorial/event',
			'com': T_Event
        },
        {
            'name': 'Bindings',
			'url': '/tutorial/bindings',
			'com': T_Bindings
        },
        {
            'name': 'Routing',
			'url': '/tutorial/routing',
			'com': T_Routing
        },
        {
            'name': 'Deploy',
			'url': '/tutorial/deploy',
			'com': T_Deploy
        }
	]

	function get_next(index) {
		if (index == menu.length - 1) {
			return false
		}
		return menu[index + 1]['url']
	}

	function get_previous(index) {
		if (index == 3) {
			return false
		}
		return menu[index - 1]['url']
	}

	menu.forEach((mn, index) => {
		if (mn.name == 'Tutorial') {
			router(mn.url, () => router.redirect('/tutorial/instalation'))
		} else if(index > 2) {
			router(mn.url, () => {body = mn.com; title = mn.name; next=get_next(index); previous=get_previous(index); tutorial=true})
		} else {
			router(mn.url, () => {body = mn.com; title = mn.name; tutorial=false})
		}
	});

	router('*', () => {body = NotFound; title = 404})
	router.start()

	window.addEventListener('scroll', () => {
		if (window.scrollY > 60) {
			navPosition = 'fixed'
			navMarginTop = '1%';
		} else {
			navPosition = 'absolute'
			navMarginTop = '10%'
		}
	})

	let timer = setInterval(() => {
		if (document.readyState == 'complete') {
			if (document.readyState == 'complete') {
				blur = 0
			}
			clearInterval(timer)
		}
	}, 100);
</script>

<div class="row mw-100 website" style="transition: all 0.4s; height: 100%; width: 100%;{blur != 0 ? `filter: blur(50px);` : ''}">
	<Navbar menu={menu} brandUrl="/" site={site}></Navbar>
	
    {#if tutorial}
		<nav aria-label="Page navigation navigationTutorial example" style="transition: all 0.4s; position: {navPosition}; right: 1%; ; top: {navMarginTop}; z-index: 5;">
			<ul class="pagination shadow-sm">
				<li class="page-item {previous == false ? 'disabled' : ''}"><a class="page-link" href="{previous}">Previous</a></li>
				<li class="page-item {next == false ? 'disabled' : ''}"><a class="page-link" href="{next}">Next</a></li>
			</ul>
		</nav>
	{/if}

	<div class="w-100" style="position: absolute; left: 0; right: 0; filter: blur(0px); margin: auto; height: 100%; top: 9%;">
		<svelte:component this={body} place={place} />
	</div>
</div>