<script>
  import Elemento from "../src/componentes/Elemento.svelte";

  let elemento = { activo: false };

  function toggle() {
    elemento.activo = !elemento.activo;
    setTimeout(() => {
      if (elemento.activo) {
        elemento.activo = false;
      }
    }, 4000);
  }
</script>

<style>

</style>

{#if elemento.activo}
  <button on:click={toggle}>Ocultar</button>
  <Elemento texto={'Maya'} />
{:else}
  <button on:click={toggle}>Mostrar</button>
{/if}
