<script>
  import { page } from "$app/stores";
  import { onMount } from "svelte";
  
  const id = $page.url.searchParams.get("id");
  // console.log(id);
  // export let data;
  let data;

  onMount(async function () {
    const response = await fetch("http://localhost:8000/api/ideas/" + id);
    if(response.status == 200)
      data = await response.json();
    else{
      console.log(response.status);
      window.location.href = '/error?ec=' + response.status;
    }
      
  });
</script>

<section>
  {#if data != null}
    <h1 class="title">{data.title}</h1>

    <h3 class="date_created">{data.created_on}</h3>

    <h3 class="creator">{data.created_by}</h3>

    <hr />
    <p class="description">{data.description}</p>

    <a href="/list">
      <button class="button">BACK</button>
    </a>
  {/if}
  <!-- {ideas_id} -->
</section>

<style>
  * {
    text-align: center;
  }

  .title {
    font-size: 3rem;
    margin-bottom: 1rem;
  }
  .creator {
    font-size: 1rem;
    font-weight: normal;
    color: rgb(202, 202, 202);
  }
  .description {
    font-size: 1.5rem;
    padding: 0 10rem;
  }

  @media (max-width: 60rem) {
    .description {
      padding: 0 1rem;
    }
  }
  section {
    max-width: 70rem;
    margin: 0 auto;
  }

  .button {
    width: 20rem;
    height: 5rem;
    font-size: 2rem;
    background-color: #09bc8a;
    border: 3px solid black;
    transition: 200ms;
    box-shadow: 7px 7px #4a665e, 11px 11px black;
  }
  .button:hover {
    transform: scale(1.03);
  }
  .button:active {
    transform: scale(0.98);
  }
</style>
