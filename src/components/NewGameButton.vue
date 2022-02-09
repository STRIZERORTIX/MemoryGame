<script>
export default {
  props: {
    newPlayer: {
      type: Boolean,
      default: true
    }
  },
  setup(props, ctx) {
    const startNewGame = () => {
      ctx.emit('start-new-game')
    }

    return {
      startNewGame
    }
  }
}
</script>

<template>
  <h1>Try This Memory Game:</h1>
  <button v-if="newPlayer" @click="startNewGame" :class="$style.button">

    Start Game
  </button>
  <button v-else @click="startNewGame" :class="$style.button">
    Restart Game
  </button>
</template>

<style module>
@import url('https://fonts.googleapis.com/css2?family=Syne+Tactile&display=swap');

h1{
  font-family: 'Syne Tactile', cursive;
  color: #000;
}
.button {
  background-color: #00e1ff;
  color: rgb(0, 0, 0);
  padding: 8px 16px 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 30px;
  font-weight: bold;
  font-family: 'Titillium Web', sans-serif;
  font-weight: bold;
  font-size: 1rem;
  border: 0;
  border-radius: 10px;
  transition: 0.2s all ease-in;
  border: 2px solid #0567e7;
}

.button:hover {
  border: 2px solid #000000;
  background-color: transparent;
  color: #000000;
}

.button:hover  {
  opacity: 1;
}

.button:hover .icon-play {
  opacity: 0;
}


.button .icon-ghost {
  position: absolute;
  left: -6px;
  opacity: 0;
}

.button .icon-play {
  position: absolute;
  left: -6px;
  opacity: 1;
}

.button-icon {
  position: relative;
  width: 24px;
  height: 24px;
}
</style>
