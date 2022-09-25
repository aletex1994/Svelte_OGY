<script lang="ts">
  import linkedinLogo from "./assets/linkedin.svg";
  import githubLogo from "./assets/github.svg";
  import Topbar from "./lib/Topbar.svelte";
  import Footer from "./lib/Footer.svelte";
  let whoami =
    "I'm a Fullstack Developer from Italy, currently working for <a href='https://www.origyn.com/' target='_blank'>Origyn Foundation</a>";
  let whatido = 
  "IT professional with several years of experience in website frontend/backend development on different website projects built from scratch, entushiast and dynamic, details oriented and proactive on problem solving."
</script>

<Topbar />
<main class="card main-content">
  <div>
    <a
      href="https://www.linkedin.com/in/alessandro-tezza-5201a721a/"
      target="_blank"
    >
      <img src={linkedinLogo} class="logo" alt="Linkedin Logo" />
    </a>
    <a href="https://github.com/aletex1994" target="_blank">
      <img src={githubLogo} class="logo" alt="Git Logo" />
    </a>
  </div>
  <h1>Alessandro Tezza</h1>
  <p>
    {@html whoami}
  </p>
  <p class="small-text">
    {@html whatido}
  </p>
</main>
<Footer/>
<style>
  .logo {
    height: 3em;
    padding: 1.5em;
    will-change: filter;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #fff);
  }
  .small-text{
    font-size: 0.8em;
  }
</style>
