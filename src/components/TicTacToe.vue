<template>
  <div class="tictactoe-board">
    <div v-for="(num, i) in 3" v-bind:key=i>
      <div v-for="(num, j) in 3" v-bind:key=j>
        <cell @click="performMove(i, j)" :value="board[i][j]"></cell>
      </div>
    </div>
  </div>
  
</template>

<script>
export default {

  data() { return {
    board: [
      ['', '', ''],
      ['', '', ''],
      ['', '', '']
    ]
  }},

  methods: {
    performMove(x, y) {
      if(this.board[x][y] !== ''){
        //Not an empty space to move
        return;
      }
      this.board[x][y] = 'x';
      this.$forceUpdate();

    }
  }

}
</script>

<style>
  .tictactoe-board {
    display: flex;
    flex-wrap: wrap;
    width: 204px;
    height: 204px;
  }
</style>
