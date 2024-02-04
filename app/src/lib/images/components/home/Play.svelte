<!-- lib/components/home/Play.svelte -->
<script>
  export let Play;
</script>

<div>
  <button>
    <span class="material-symbols-outlined settings">settings</span>
  </button>
  <span></span>
  <button>
    <span class="material-symbols-outlined play">stadia_controller</span>
    <p>Jouer</p>
  </button>
</div>

<style>
  @import url(/stylesheets/common.css);

  div {
    background-color: var(--theme-color);
    padding: 5px;
    border-radius: 25px;
    width: 250px;
    height: 35px;
    display: flex;
    flex-flow: row nowrap;
    gap: 10px;
    box-shadow: -5px 5px 5px var(--theme-shadow);
  }

  div > button {
    background-color: transparent;
    color: white;
    display: flex;
    flex-flow: row nowrap;
    justify-content: center;
    align-items: center;
  }

  div>button:hover {
    cursor: pointer;
  }

  div > button span {
    width: 35px;
    height: 35px;
    display: flex;
    justify-content: center;
    font-weight: lighter;
    align-items: center;
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

  div > span {
    border: solid 1px white;
  }

  .settings {
    min-width: unset;
    width: 35px;
    font-size: 40px;
    z-index: 1;
  }

  .play {
    font-size: 45px;
    min-width: unset;
    width: 35px;
  }
</style>
