<script>
  import Elemento from "../src/componentes/Elemento.svelte";
  import ElementoBotonDos from "../src/componentes/ElementoBotonDos.svelte";

  let elemento = { activo: false };

  function MostrarElemento() {
    elemento.activo = !elemento.activo;
    setTimeout(() => {
      if (elemento.activo) {
        elemento.activo = false;
      }
    }, 4000);
  }


let elementoDos = { activo: false };

  function MostrarElementoDos() {
    elementoDos.activo = !elementoDos.activo;
    setTimeout(() => {
      if (elementoDos.activo) {
        elementoDos.activo = false;
        
      }
    }, 4000);
  }



</script>

<style>

</style>



{#if elemento.activo}
	<button on:click={MostrarElemento}>Ocultar</button>
  <Elemento texto={'Maya'} />
{:else if elementoDos.activo }
  <button disabled={true} on:click={MostrarElemento}>Mostrar</button>
{:else}
  <button disabled={false} on:click={MostrarElemento}>Mostrar</button>
{/if}



{#if elementoDos.activo}
	<button on:click={MostrarElementoDos}>Ocultar</button>
  <ElementoBotonDos texto={'Nahuátl'} />
{:else if elemento.activo }
  <button disabled={true} on:click={MostrarElementoDos}>Mostrar</button>
{:else}
  <button disabled={false} on:click={MostrarElementoDos}>Mostrar</button>
{/if}



