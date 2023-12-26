<script>
  import welcome from "$lib/images/svelte-welcome.webp";
  import welcome_fallback from "$lib/images/svelte-welcome.png";
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
  <div class="text-box">
    <p>Welcome to</p>
    <h1>CHEWATA</h1>
    <h3>Lets play together</h3>
  </div>
</section>

<style>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 20;
  }

  div {
    justify-content: center;
    align-items: center;
  }

  .text-box {
    font-family: "Poppins", sans-serif;
    color: #fff;
    position: absolute;
  }

  .text-box p {
    margin-left: 20px;
    font-size: 50px;
    font-weight: 600;
  }
  /* .text-box h1 {
    font-size: 90px;
    line-height: 60px;
    margin-left: -10px;
    font-weight: 900;
  } */
  .text-box h3 {
    font-size: 40px;
    font-weight: 500;
  }

  h1 {
    animation: text-shadow 1.5s ease-in-out infinite;
    font-size: 90px;
    margin-left: -80px;
    font-weight: 900;
    line-height: 1;
  }

  h1:hover {
    animation-play-state: paused;
  }

  @keyframes text-shadow {
    0% {
      transform: translateY(0);
      text-shadow:
        0 0 0 #0c2ffb,
        0 0 0 #2cfcfd,
        0 0 0 #fb203b,
        0 0 0 #fefc4b;
    }

    20% {
      transform: translateY(-1em);
      text-shadow:
        0 0.125em 0 #0c2ffb,
        0 0.25em 0 #2cfcfd,
        0 -0.125em 0 #fb203b,
        0 -0.25em 0 #fefc4b;
    }

    40% {
      transform: translateY(0.5em);
      text-shadow:
        0 -0.0625em 0 #0c2ffb,
        0 -0.125em 0 #2cfcfd,
        0 0.0625em 0 #fb203b,
        0 0.125em 0 #fefc4b;
    }

    60% {
      transform: translateY(-0.25em);
      text-shadow:
        0 0.03125em 0 #0c2ffb,
        0 0.0625em 0 #2cfcfd,
        0 -0.03125em 0 #fb203b,
        0 -0.0625em 0 #fefc4b;
    }

    80% {
      transform: translateY(0);
      text-shadow:
        0 0 0 #0c2ffb,
        0 0 0 #2cfcfd,
        0 0 0 #fb203b,
        0 0 0 #fefc4b;
    }
  }

  @media (prefers-reduced-motion: reduce) {
    * {
      animation: none !important;
      transition: none !important;
    }
  }
</style>
