<script>
	import { enhance } from '$lib/form';
	import { scale } from 'svelte/transition';
	import { flip } from 'svelte/animate';
	import { json } from '@sveltejs/kit';
	import { dataset_dev, prevent_default } from 'svelte/internal';
	import {onMount} from 'svelte';
	import { connected, web3, selectedAccount, chainId, chainData, defaultEvmStores } from 'svelte-web3'
	// import { login } from 'sveltekit-web3auth/web3auth/Web3Auth.svelte';

	onMount(async () => {
		defaultEvmStores.setProvider()
	fetch(`https://express-api.codeboxxtest.xyz/NFT/getWalletTokens/0x5f927157539C9f690F1f381c8Ba6Add22d84325C`)
	.then(function(response){
		return response.json();
	})
	.then(function(data) {
		for(let i=0; i<data.length; i++) {
			document.getElementById("portfolio").innerHTML +=
			(data[i].name + " | " + data[i].description);
			document.getElementById("image").setAttribute("src", data[i].image);
			return null;
		}
	})
	.catch(function(err) {
		console.log(err);
	});
});
</script>

<svelte:head>
	<title>Portfolio</title>
	<meta name="description" content="A todo list app" />
</svelte:head>

<body>
	<h1>WALLET PORTFOLIO</h1>
	<p id="portfolio"></p>
	<div>
		<img src="" id="image" alt="image" />
	</div>
</body>

<style>
	body {
		background-color: black;
	}

	h1 {
		color: white;
		font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
	}

	th {
		color: white;
	}

	tr {
		color: white;
	}

	p {
		color: white;
		text-align: center;
		font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
	}

	img {
		height: 300px;
		width: 300px;
	}

	div {
		display: flex;
		justify-content: center;
	}

	
</style>
