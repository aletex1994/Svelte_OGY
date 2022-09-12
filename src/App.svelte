<script lang="ts">
  import linkedinLogo from './assets/linkedin.svg'
  import githubLogo from './assets/github.svg' 
  import Counter from './lib/Counter.svelte'
  import Topbar from './lib/Topbar.svelte';
</script>
<Topbar/>
<main class="card main-content">
  <div>
    <a href="https://www.linkedin.com/in/alessandro-tezza-5201a721a/" target="_blank"> 
      <img src={linkedinLogo} class="logo" alt="Linkedin Logo" />
    </a>
    <a href="https://github.com/aletex1994" target="_blank"> 
      <img src={githubLogo} class="logo" alt="Git Logo" />
    </a>
  </div>
  <h1>Alessandro Tezza</h1>

  <div class="card">
    <Counter />
  </div>

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank">SvelteKit</a>, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">
    Click on the Vite and Svelte logos to learn more
  </p>
</main>

<style>
  .logo {
    height: 3em;
    padding: 1.5em;
    will-change: filter;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #000);
  }
  .read-the-docs {
    color: rgb(186, 186, 186);
  }
</style>