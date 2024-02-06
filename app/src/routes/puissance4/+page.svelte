<script>
// @ts-nocheck

  let grid = Array.from({ length: 6 }, () => Array(7).fill(null));
  let currentPlayer = 'red';
  let winner = null;

  let currentPlayerBorderStyle = {
    borderColor: 'red'
  };

  $: currentPlayerBorderStyle.borderColor = currentPlayer;
  $: winnerMessage = winner ? `${winner.toUpperCase()} a gagné !` : `Tour du joueur ${currentPlayer.toUpperCase()}`;

  function play(column) {
    if (winner) return;

    for (let row = 5; row >= 0; row--) {
      if (!grid[row][column]) {
        grid[row][column] = currentPlayer;
        checkForWinner(row, column);
        currentPlayer = currentPlayer == 'red' ? 'yellow' : 'red';
        break;
      }
    }
  }

  function checkForWinner(row, column) {
    if (
      checkDirection(row, column, 1, 0) || 
      checkDirection(row, column, 0, 1) ||      
      checkDirection(row, column, 1, 1) || 
      checkDirection(row, column, 1, -1)   
    ) {
      winner = currentPlayer;
      window.alert(`Le joueur ${currentPlayer.toUpperCase()} a gagné !`);
    }
  }

  function checkDirection(row, column, rowDir, colDir) {
    const count = (r, c) => grid[r] && grid[r][c] === currentPlayer;

    let consecutive = 1;
    for (let i = 1; i <= 3; i++) {
      const newRow = row + i * rowDir;
      const newCol = column + i * colDir;

      if (count(newRow, newCol)) {
        consecutive++;
      } else {
        break;
      }
    }

    for (let i = 1; i <= 3; i++) {
      const newRow = row - i * rowDir;
      const newCol = column - i * colDir;

      if (count(newRow, newCol)) {
        consecutive++;
      } else {
        break;
      }
    }

    return consecutive >= 4;
  }
</script>

<style>
  h1 {
    border: 2px solid #ccc;
    padding: 10px;
    border-radius: 5px;
  }

  .board {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 5px;
  }

  .cell {
    width: 50px;
    height: 50px;
    border: 1px solid #ccc;
    border-radius: 50%;
    cursor: pointer;
    background-color: #fff;
  }

  .red {
    background-color: red;
  }

  .yellow {
    background-color: yellow;
  }
</style>

<main>
  <h1 style="border-color: {currentPlayerBorderStyle.borderColor}">{winnerMessage}</h1>

  <div class="board">
    {#each grid as row, rowIndex}
      {#each row as cell, columnIndex}
      <div class="cell" on:click={() => play(columnIndex)} class:red={cell==='red'} class:yellow={cell==='yellow'}></div>
      {/each}
    {/each}
  </div>
</main>