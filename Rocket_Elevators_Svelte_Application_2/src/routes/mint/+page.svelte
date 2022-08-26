<script src="https://cdn.jsdelivr.net/npm/web3@latest/dist/web3.min.js">
import {writable} from "svelte/store";
import {onMount} from 'svelte';
// import post from "sveltekit-web3auth/web3auth/routes/auth/users";
// import { login } from "sveltekit-web3auth/web3auth/Web3Auth.svelte";

// var window;
var Account;
let walletConnected = false;
const connectAccount = async () =>  {
        await ethereum.request({ method: 'eth_requestAccounts'})
		.then(accounts => {
            console.log(accounts)
           Account = accounts[0];
		   walletConnected = true;
            console.log('my wallet address is:', Account);
            
            
            ethereum.request({ method: 'eth_getBalance', params: [Account, 'latest']}).then( result => {
                console.log("wallet address:", result);
                let wei = parseInt(result,16);
                let balance = wei / (10**18);
                console.log('my ballance is:', balance + " eth")
            })
        })
    };
	
	 onMount(async () => {
	fetch(`https://express-api.codeboxxtest.xyz/NFT/gift/0x5f927157539C9f690F1f381c8Ba6Add22d84325C`)
	.then(function(response){
		console.log('this account is eligible:', response);
		return response.json();
	})
	.then(function(data) {
			for(let i=0; i<data.length; i++) {
				(data[i].redirect);
				console.log(data[i].redirected);
				eligibility.set(data)
				return data[i].redirected;
			}
		})
	.catch(function(err) {
		console.log(err);
	});
	});

	const buyNft = async () => {
		const res = await fetch(`https://express-api.codeboxxtest.xyz/NFT/buyWithRocket/0x5f927157539C9f690F1f381c8Ba6Add22d84325C`, {
			method: "POST"
		});
		console.log('this response is:', res);
	}

	const freeNft = async () => {
		const res = await fetch(`https://express-api.codeboxxtest.xyz/NFT/gift/0x5f927157539C9f690F1f381c8Ba6Add22d84325C`, {
			method: "POST"
		});
		console.log('this response is:', res);
	}
	

</script>

<svelte:head>
	<title>About</title>
	<meta name="description" content="About this app" />
</svelte:head>

<body>
	<div id="rockets">
		<img src="blue_rockets.jpeg" alt="blue"/>
		<img src="yellow_rocket.jpeg" alt="yellow"/>
		<img src="grey_rocket.jpeg" alt="grey" />
	</div>

	{#if walletConnected}
	  <div class="btn1">
		<div class="accountDisplay">
		  CONNECTED ACCOUNT: {Account}
	  
		</div>
	  </div>
	{:else} 
	  <div class="btn1">
		<button id="loginButton" on:click={connectAccount}>CONNECT WITH METAMASK</button>
	  </div>
	{/if}
	  <!-- {#if walletConnected === true} -->
	<button id="freeNFT" on:click={freeNft}>FREE NFT?</button>
	<button id="buyNft" on:click={buyNft}>BUY NFT</button>
</body>

<style>

	body {
		background-color: black;
	}
	

	button {
		margin-left: 260px;
		background-color: red;
		color: white;
		outline: none;
		width: 50%;
		position: relative;
		margin-bottom: 10px;
	}

	#rockets {
		margin-left: 125px;
	}
</style>
