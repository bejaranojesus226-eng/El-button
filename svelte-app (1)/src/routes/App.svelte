<script>
  let count = 0;
  const limite = 5;
  let mostrarImagen = false;

  let audioUrl = "https://www.soundjay.com/human/fart-01.mp3";
  let audio = new Audio(audioUrl);

  function clickPedo() {
    count += 1;
    audio.currentTime = 0;
    audio.play();

    if (count === limite) {
      mostrarImagen = true;
    }
  }
</script>

<main>
  <h1>= Contador de Pedos =</h1>
  <p class="contador">Has hecho <span>{count}</span> pedos</p>
   
  <button on:click={clickPedo} class="btn">
    = Tirarse un pedo
  </button>

  {#if mostrarImagen}
    <div class="imagen">
      <img src="https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExbTV5cmN6d29iMnNpbm1vYmkyZW9oN2RqcHQ3MWtsaGd0eDYydWV5dyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/okfvUCpgArv3y/giphy.gif" alt="¡Tremendo pedo!" />
      <p>Troliado</p>
    </div>
  {/if}
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    background: linear-gradient(135deg, black, #ffe0b2);
    font-family: 'Comic Sans MS', cursive, sans-serif;
    text-align: center;
  }

  h1 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    color: red;
    text-shadow: 2px 2px #ffcc80;
  }

  .contador {
    font-size: 1.5rem;
    margin-bottom: 1.5rem;
  }

  .contador span {
    font-weight: bold;
    color: #d84315;
  }

  .btn {
    background: #ff7043;
    color: black;
    border: none;
    padding: 1rem 2rem;
    border-radius: 15px;
    font-size: 1.2rem;
    cursor: pointer;
    transition: transform 0.1s ease, background 0.3s ease;
  }

  .btn:hover {
    background: yellow;
    transform: scale(1.05);
  }

  .imagen {
    margin-top: 2rem;
    animation: pop 0.5s ease;
  }

  .imagen img {
    max-width: 250px;
    border-radius: 10px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.3);
  }

  @keyframes pop {
    from { transform: scale(0.5); opacity: 0; }
    to { transform: scale(1); opacity: 1; }
  }
</style>