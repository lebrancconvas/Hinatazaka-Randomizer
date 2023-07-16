<script lang="ts">
  import Hinata from '../data/hinatazaka.json';
  import Card from '../lib/card.svelte';
  let name = Hinata[0].name;
  let image = Hinata[0].imgURL;
  let isFlipped = false;
  let isButtonDisabled = false;
  const random = () => {
    const random = Math.floor(Math.random() * Hinata.length);
    name = Hinata[random].name;
    image = Hinata[random].imgURL;
  };

  const spin = () => {
    if(!isFlipped) {
      isFlipped = true;
      isButtonDisabled = true;
      setTimeout(() => {
        isFlipped = false;
        isButtonDisabled = false;
      }, 1000)
    }
  }
  console.log(`Image: ${image}`);
</script>

<svelte:head>
  <title>Hinatazaka Randomizer</title>
</svelte:head>

<main>
  <header>
    <div>
      <h1>Hinatazaka Randomizer</h1>
    </div>
    <div>
      <h2>Just a random web that you can random your member from Hinatazaka46</h2>
    </div>
  </header>
  <div id="card-section">
    <Card name={name} image={image} isFlipped={isFlipped} />
  </div>
  <div id="action-section">
    <button id="random-button" on:click={random} on:click={spin} disabled={isButtonDisabled}>Random !</button>
  </div>
  <footer>
    <div>
      <p>Copyright 2023, Made by <a href="https://github.com/lebrancconvas" target="_blank">Poom Yimyuean (lebrancconvas)</a></p>
    </div>
  </footer>
</main>

<style lang="css" scoped>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Noto Sans JP', sans-serif;
  }

  header, footer {
    text-align: center;
  }


  button {
    outline: none;
    border: none;
    border-radius: 7px;
    cursor: pointer;
  }

  button:active {
    transform: scale(0.97);
  }

  #action-section {
    /* outline: 2px solid black; */
    display: flex;
    justify-content: center;
    align-items: center;
  }

  #random-button {
    width: 10%;
    height: 50px;
    margin-top: 50px;
    background-color: #16cd7b;
    font-size: 18px;
    box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.5);
  }


  footer {
    position: fixed;
    bottom: 0;
    text-align: center;
    width: 100%;
    height: 50px;
  }
</style>
