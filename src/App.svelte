<script>
  import Elemento from "../src/componentes/Elemento.svelte";
  import ElementoBotonDos from "../src/componentes/ElementoBotonDos.svelte";

  let elemento = { activo: false };

  function toggle() {
    elemento.activo = !elemento.activo;
    setTimeout(() => {
      if (elemento.activo) {
        elemento.activo = false;
      }
    }, 4000);
  }

//let disabled = { activo: false };

let elementoDos = { activo: false };

  function toggleSecond() {
    elementoDos.activo = !elementoDos.activo;
    setTimeout(() => {
      if (elementoDos.activo) {
        elementoDos.activo = false;
        //disabled.activo = true;
      }
    }, 4000);
  }



</script>

<style>

</style>

<!-- {#if elemento.activo}
  <button on:click={toggle}>Ocultar</button>
  <Elemento texto={'Maya'} />
{:else}
  <button on:click={toggle}>Mostrar</button>
{/if} -->

{#if elemento.activo}
	<button on:click={toggle}>Ocultar</button>
  <Elemento texto={'Maya'} />
{:else if elementoDos.activo }
  <button disabled={true} on:click={toggle}>Mostrar</button>
{:else}
  <button disabled={false} on:click={toggle}>Mostrar</button>
{/if}


<!-- {#if elementoDos.activo}
  <button on:click={toggleSecond}>Ocultar</button>
  <ElementoBotonDos texto={'Nahuátl'} />
{:else}
  <button disabled={toggle= true} on:click={toggleSecond}>Mostrar</button>
{/if} -->

{#if elementoDos.activo}
	<button on:click={toggleSecond}>Ocultar</button>
  <ElementoBotonDos texto={'Nahuátl'} />
{:else if elemento.activo }
  <button disabled={true} on:click={toggleSecond}>Mostrar</button>
{:else}
  <button disabled={false} on:click={toggleSecond}>Mostrar</button>
{/if}



