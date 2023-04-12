<script>
  import { page } from "$app/stores";

  let links = ["", "add", "list", "about"];
</script>

<header>
  <div class="nav_container">
    {#each links as link_val, i}
      <div class="nav_link" class:page={$page.url.pathname === "/" + link_val}>
        <a href={"/" + link_val}>{link_val === "" ? "home" : link_val}</a>
      </div>
    {/each}
  </div>
  <hr class="divider" />
</header>

<style>
  header {
    margin: 20px 40px;
    z-index: 5000;
  }

  .divider {
    margin: 5px auto;
    max-width: 80rem;
  }
  .nav_container {
    display: flex;
    max-width: 80rem;
    margin: 0px auto;
    flex-direction: row;
    /* background-color: var(--primary-color); */
    height: 2.25rem;
  }

  .nav_link {
    display: flex;
    flex: 1;
    justify-content: space-evenly;
    align-items: center;
    /* padding: 0 5rem; */
    font-size: 1.5rem;
  }

  .nav_link > * {
    color: var(--text);
    text-decoration: none;
  }

  .page {
    font-weight: bold;

  }
  .page > *{
		text-decoration: underline ;
  }
</style>
