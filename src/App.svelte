
<script>
/* 
mostrar, temporalidad del texto, regrese al estado inicial
funcion que contenga el timeout
 */

import Elemento from '../src/componentes/Elemento.svelte';


	let elemento = { activo: false };

	function toggle() {
		elemento.activo = !elemento.activo;

		//setTimeout(toggle,5000)
		
	}
	
	setTimeout(() => {
  toggle()  
},5000)


</script>


<style>
</style>


{#if elemento.activo}
	<button on:click={toggle}>
		Ocultar
	</button>
	<Elemento texto={'Maya'}/>
	
{:else}
	<button on:click={toggle}>
		Mostrar
	</button>
	
{/if}



