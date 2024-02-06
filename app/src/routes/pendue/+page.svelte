<script>
  // @ts-nocheck

  let userInput = '';
  let mot_a_trouver = 'Test';
  let traitIndexes = Array(mot_a_trouver.length).fill(false); // Tableau pour suivre quels indices ont été trouvés

  const alphabet = 'abcdefghijklmnopqrstuvwxyz'.split('');

  function addToInput(letter) {
    userInput += letter;
    updateTraitIndexes();
  }

  function clearInput() {
    userInput = '';
    updateTraitIndexes();
  }

  function handleEnter() {
    alert(`Vous avez saisi : ${userInput}`);
    // Vous pouvez également effectuer d'autres actions avec la valeur saisie
    clearInput();
  }

  function updateTraitIndexes() {
    traitIndexes = Array(mot_a_trouver.length).fill(false);
    for (let i = 0; i < userInput.length && i < mot_a_trouver.length; i++) {
      if (userInput[i] === mot_a_trouver[i]) {
        traitIndexes[i] = true;
      }
    }
  }
</script>

<style>
  button {
    margin: 5px;
    padding: 10px;
    font-size: 16px;
  }

  .trait {
    display: inline-block;
    width: 10px;
    height: 2px;
    background-color: black;
    margin: 0 2px;
  }
</style>

<div>
  <!-- <div>
    {#each mot_a_trouver.split('') as letter, index}
      {#if traitIndexes[index]}
        <span class="trait"></span>
      {:else}
        <span>{userInput[index]}</span>
      {/if}
    {/each}
  </div> -->

  {#each alphabet as letter}
    <button on:click={() => addToInput(letter)}>{letter}</button>
  {/each}

  <button on:click={clearInput}>Effacer</button>
  <button on:click={handleEnter}>Entrer</button>

  <div>
    <p>Valeur saisie : {userInput}</p>
  </div>
</div>
