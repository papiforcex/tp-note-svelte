<!-- lib/components/home/Stats.svelte -->
<script>
  export let Stats;
</script>

<div>
  <button on:click="{() => confirm('Aucune statistique n\'est disponible pour l\'instant. Pensez à jour pour enregistrer votre score!') ? window.open('/puissance4', '_self') : null}">
    <span class="material-symbols-outlined play">bar_chart</span>
    <div></div>
    <p>Statistiques</p>
  </button>
</div>

<style>
  @import url(/stylesheets/common.css);

  div:has(> button) {
    background-color: var(--theme-sub);
    padding: 5px;
    border-radius: 25px;
    width: 250px;
    height: 35px;
    display: flex;
    flex-flow: row nowrap;
    box-shadow: -5px 5px 5px var(--theme-shadow);
  }

  div > button {
    background-color: transparent;
    color: white;
    display: flex;
    flex-flow: row nowrap;
    justify-content: center;
    align-items: center;
    gap: 10px;
  }

  div > button > span {
    width: 35px;
    display: flex;
    justify-content: center;align-items: center;
    font-size: 48px;
    height: 35px;
  }

  div > button > div {
    height: 35px;
    border: solid 1px white;
  }

  div > button:hover {
    cursor: pointer;
  }

  div > button:has(> p) {
    width: 100%;
  }

  div > button:has(> p) p {
    text-transform: uppercase;
    font-weight: lighter;
    font-size: 24px;
    width: 100%;
    text-align: center;
  }
</style>
