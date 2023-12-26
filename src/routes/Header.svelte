<script>
  import { page } from "$app/stores";
  import logo from "$lib/images/logo1.svg";
  import github from "$lib/images/github.svg";
</script>

<header>
  <a href="/">
    <img src={logo} class="logo" alt="home" />
  </a>

  <!-- <label for="" class="icons">
    <i class="bx bx-menu"></i>
  </label> -->
  <!-- <a href="/" class="logo">Logo</a> -->
  <nav class="navbar">
    <li aria-current={$page.url.pathname === "/" ? "page" : undefined}>
      <a href="/">Home</a>
    </li>
    <li aria-current={$page.url.pathname === "/about" ? "page" : undefined}>
      <a href="/about">About</a>
    </li>
    <li
      aria-current={$page.url.pathname.startsWith("/Games")
        ? "page"
        : undefined}
    >
      <a href="/games">Games</a>
    </li>
  </nav>
</header>

<style>
  header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding: 1.2rem 10%;
    background: rgba(0, 0, 0, 0.1);
    background: rgba(255, 255, 255, 0.06);
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(8.8px);
    -webkit-backdrop-filter: blur(8.8px);
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 100;
  }

  a {
    position: relative;
    display: flex;
    top: 0;
    left: 0;
  }

  a img {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 3em;
    height: 3em;
    object-fit: cover;
  }

  .icons {
    position: absolute;
    right: 15%;
    font-size: 2.1rem;
    color: aqua;
    cursor: pointer;
    display: none;
  }

  nav {
    display: flex;
    justify-content: center;
  }

  ul {
    position: relative;
    top: 0;
    right: 50%;
    height: 3em;
    display: flex;
    justify-content: center;
    align-items: center;
    list-style: none;

    background-size: contain;
  }

  ul li {
    top: 0;
    right: 0;
    position: relative;
    display: flex;
    height: 100%;
    margin: 1rem;
    color: aqua;
  }

  li[aria-current="page"]::before {
    --size: 6px;
    content: "";
    width: 0;
    height: 0;
    position: absolute;
    top: 0;
    left: calc(50% - var(--size));
    border: var(--size) solid transparent;
    border-top: var(--size) solid var(--color-theme-1);
  }

  nav a {
    display: flex;
    height: 100%;
    align-items: center;
    padding: 0 0.5rem;
    color: aqua;
    font-weight: 700;
    font-size: 0.8rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    text-decoration: none;
    transition: color 0.2s linear;
  }

  a:hover {
    color: var(--color-theme-1);
  }

  @media (max-width: 900px) {
    header {
      padding: 1.3rem 5%;
    }
  }
  @media (max-width: 700px) {
    .icons {
      display: block;
    }

    ul {
      position: absolute;
      top: 100%;
      left: 0;
      width: 100%;
      height: 17.7rem;
      background: red;
    }
    nav a {
      display: block;
    }
  }
</style>
