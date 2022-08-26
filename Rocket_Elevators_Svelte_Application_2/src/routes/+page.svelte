<script>
	// import Counter from 'sveltekit-web3auth/Counter.svelte';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>




<html lang="en">

	<!-- NAVBAR -->

	<body id="body">
		<div id="mission">

		  <!-- TOP SECTION -->
		  <div id="topPage">
			  <img id="topImg" src="sky_club.jpeg" />
			  <h4 id="skyClub">
				  A limited NFT collection where the token itself doubles as your membership to a sky
				  club for Rocket owners. The club is open! Take off with us.
				</h4>
		  </div>

		<div id="svelte">%sveltekit.body%</div>
	</body>
</html>

<style>
	* {
    padding: 0;
    margin: 0;
  }

  #mint {
	padding: 0 25px 0 0;
	color: red;
    text-decoration: none;
	padding-left: 500px;
	font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  }

  #portfolio {
	padding: 0 25px 0 0;
	color: red;
    text-decoration: none;
	padding-right: 500px;
	font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  }

  #body {
	  background-color: rgb(0, 0, 0);
  }

  #svelte {
	  display: none;
  }


  h1 {
	  color: #ffffff;
  }

  #list {
	color: #ffffff;
  }

  #skyClub {
	  color: #ffffff;
	  text-align: center;
	  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
	  padding-top: 10px;
	  padding-bottom: 10px;
  }

  #rareRockets {
	color: #ffffff;
	text-align: center;
  }

  #navImg {
	  align-items: center;
	  width: 200px;
	  height: 50px;
	  /* padding-left: 625px; */
  }

  #topImg {
	width: 800px;
	height: 600px;
	padding: 100px 0 0 100px;
  }

  #footer {
	  margin-top: 10px;

  }
</style>
