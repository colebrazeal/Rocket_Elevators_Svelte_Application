<script>
	// import Header from 'sveltekit-web3auth/header/Header.svelte';
	import Header from '$lib/header/Header.svelte';
	import '../app.css';
</script>

<Header />

<main>
	<slot />
</main>

<footer>
	<div id="seperator" ></div>
	<div id="footer">
		<h4 id="list">GET ON THE LIST</h4>
		<input type="email" name="email" placeholder="Email Address" />
		<button>SUBMIT</button>
	</div>
</footer>

<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 40px;
		margin-top: 10px;
	}

	#list {
		color: white;
		text-align: center;
	}

	button {
		background-color: red;
		color: white;
		outline: none;
	}

	#seperator {
	  content: "";
	  position: relative;
	  background-color: red;
	  height: 2px;
	  width: 100%;
	  left: 0;
	  margin-bottom: 10px;
  }

	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	}


</style>
