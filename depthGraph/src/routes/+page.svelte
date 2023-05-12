<script>
	var adyacencia = ''
	var inicio = 0
	var destino = 1
	var camino = ''

	const calculate = async() =>{
		const response = await fetch('http://127.0.0.1:5000/profundidad?ady='+adyacencia+'&inicio='+inicio+'&destino='+destino)
		const data = await response.json()
		console.log(data)
		camino = data.camino
	}

	$: if (camino) (console.log(camino));
</script>


<div class="container">
	<h2>Por favor digite su lista de adyacencia en una matriz expresada en sus files y culomnas con llaves y comas</h2>
	<h4>de la sigueinte manera [[1,3],[0,4],[4],[0,1],[0,1,2]]</h4>
	<input type="" class="inputA" bind:value={adyacencia}>
	<h2>{adyacencia}</h2>
	
	<h2>Digite el nodo de inicio</h2>
	<input type="" class="inputA" bind:value={inicio}>
	<h2>Digite el nodo destino</h2>
	<input type="" class="inputA" bind:value={destino}>
	<button on:click={calculate}>CALCULAR</button>
	<h2>{camino}</h2>
</div>

<style>
	.inputA{
		width: 40%;
		border-radius: 20px;
	}
	.container{
		width: 100%;
		height: 90vh;
		margin: 0 auto;
		padding: 0;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	h2{
		color:black;
	}

</style>
