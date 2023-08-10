<script>
	import { page } from '$app/stores';
	import { fly } from 'svelte/transition';

	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-hamlindigo.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';

	import Header from '../lib/header.svelte';
	import OpenCart from '../lib/openCart.svelte';

</script>


<Header />
<OpenCart />
<slot />

<h1>hola</h1>
<!-- {#key $page.url.pathname}
	<div class="container h-full mx-auto flex justify-center items-center" in:fly={{ x: -200, duration: 500 }}
	out:fly={{ x: 200, duration: 500}}>
	</div>
{/key} -->
