<script>
// @ts-nocheck

  import Play from "$lib/components/home/Play.svelte";
  import Stats from "$lib/components/home/Stats.svelte";
  import Credits from "$lib/components/home/Credits.svelte";
    function parentFunction() {
        window.open('/puissance4', '_self');
    }
</script>

<div class="page-home">
  <h1>Bienvenue sur puissance pendue!</h1>
  <div>
    <Play on:childClick={() => parentFunction()}/>
    <Stats/>
    <Credits/>
  </div>
</div>
