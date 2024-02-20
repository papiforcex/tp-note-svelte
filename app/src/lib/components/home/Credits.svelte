<!-- lib/components/home/Credits.svelte -->
<script>
  export let Credits;
</script>

<div>
  <button on:click="{() => alert('Ce projet a été créé par Fayad MAOULANA, Théo BENET-CHAPARD et Kylian PRÉVOT :)')}">
    <span class="material-symbols-outlined play">person</span>
    <div></div>
    <p>Crédits</p>
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
