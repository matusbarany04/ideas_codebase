<script>
  
  import { onMount } from "svelte";

import cat from '$lib/images/cat.gif';
let error_code= "...";
  onMount(() => {
    const urlSearchParams = new URLSearchParams(window.location.search);
    error_code = urlSearchParams.get('ec');
  });

</script>


<div>
	<img src={cat} alt="">
	<h1>Error {error_code != null ? error_code : ''}</h1>
	
	<h2>Have you tried turning it off and on again?</h2>
	
	<a href="/" class="safety">back to safety</a>
</div>

<style>
  * {
    text-align: center;
    font-size: 4rem;
  }
  h2 {
    font-size: 2rem;
	font-weight: normal;
  }
  .safety {
    font-size: 1.5rem;
    color: #09bc8a;
  }
  div{
	flex: 1;
	display: flex;
	flex-direction: column;
	justify-content: center;
  }
  img{
	width: 100%;
	max-width: 30rem;
	margin: 0 auto;
  }
</style>
