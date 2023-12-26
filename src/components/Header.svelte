<script>
  import logo from "$lib/images/logo1.svg";
  let isMenuOpen = false;
  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }

  let current = 0;
</script>

<div class="navbar">
  <a href="/">
    <img src={logo} class="logo" alt="home" />
  </a>
  <nav class:open={isMenuOpen}>
    <ul>
      <li on:click={() => (isMenuOpen = false)}>
        <a class:current={current === 0} on:click={() => (current = 0)} href="/"
          >Home <span></span></a
        >
      </li>
      <li on:click={() => (isMenuOpen = false)}>
        <a
          class:current={current === 1}
          on:click={() => (current = 1)}
          href="/Games">Games <span></span></a
        >
      </li>
      <li on:click={() => (isMenuOpen = false)}>
        <a
          class:current={current === 2}
          on:click={() => (current = 2)}
          href="/about">About <span></span></a
        >
      </li>
      <li on:click={() => (isMenuOpen = false)} class="ME">
        <a
          class:current={current === 3}
          on:click={() => (current = 3)}
          href="/me">ME</a
        >
      </li>
    </ul>
  </nav>
  <button class="burger" on:click={toggleMenu}>
    <div class="bar">
      <i class="bx bx-menu"></i>
    </div>
  </button>
</div>

<style>
  .navbar {
    font-family: "Poppins", sans-serif;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background: rgba(0, 0, 0, 0.1);
    background: rgba(255, 255, 255, 0.06);
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(8.8px);
    -webkit-backdrop-filter: blur(8.8px);
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    height: 5rem;
    z-index: 1;
  }

  .logo {
    margin-left: 5vw;
    width: 3em;
    height: 3em;
  }

  nav {
    font-family: "Poppins", sans-serif;
    display: none;
    font-family: Poppins;
  }

  nav.open {
    display: block;
    position: absolute;
    top: 100%;
    left: 0;
    background: rgba(0, 0, 0, 0.4);
    width: 100%;
    z-index: 1;
  }

  @media only screen and (max-width: 768px) {
    nav {
      opacity: 0;
      display: block;
      position: absolute;
      top: 100%;
      left: 100%;
      background: rgba(0, 0, 0, 0.8);

      width: 100%;
      transition: all 200ms ease-in-out;
      z-index: 1;
    }
    nav.open {
      opacity: 1;
      left: 0;
    }
  }

  ul {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    gap: 5vh;
    margin-top: 2vh;
    margin-bottom: 4vh;
    list-style: none;
    font-size: 1.1rem;
  }

  nav a:hover {
    color: aliceblue;
  }

  nav a span {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
    border-bottom: 2px solid aliceblue;
    border: 15px;
  }
  ul .current {
    position: relative;
  }

  .current::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 2px;
    background-color: lightblue;
    opacity: 20%;
  }

  /* .ME {
    background-color: aqua;
    padding: 0.6rem;
    border-radius: 10px;
    font-weight: 500;
  } */

  .ME {
    border: none;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1rem;
    color: white;
    background-color: blueviolet;
    border-radius: 100px;
    padding: 10px 30px 10px 30px;
    transform-origin: center;
    position: relative;
    overflow: hidden;
    cursor: pointer;
  }

  .ME::before {
    content: " ";
    position: absolute;
    top: 0px;
    width: 40px;
    height: 40px;
    transform: skewX(40deg) translateX(-90px);
    background-color: rgba(255, 255, 255, 0.411);
    z-index: 99;
    transition: 0.8s cubic-bezier(0.97, 0.02, 0.44, 0.99);
  }

  .ME:hover::before {
    transform: skewX(40deg) translateX(100px);
    animation: btnshine 1s cubic-bezier(0.97, 0.02, 0.44, 0.99) infinite;
  }

  .burger {
    height: 28px;
    aspect-ratio: 1;
    border: 2px solid cornflowerblue;
    background-color: transparent;
    border-radius: 5px;
    margin-right: 6vw;
  }

  @media only screen and (min-width: 768px) {
    .logo {
      margin-left: 3vw;
    }
    .burger {
      display: none;
    }

    nav {
      display: block;
      position: relative;
    }
    ul {
      margin: 0;
      flex-direction: row;
      gap: 2vw;
    }
    .ME {
      margin-inline: 2vw;
    }
  }
</style>
