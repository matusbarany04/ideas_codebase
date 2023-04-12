<script>
  import Textarea_bg from "$lib/images/textarea_bg.png";
  import { onDestroy } from 'svelte';
  import { tweened } from 'svelte/motion';
  import { cubicOut } from 'svelte/easing';
  import { subscribe } from "svelte/internal";
  import { writable } from 'svelte/store';

  function isFormValid(data) {
    // if (!isRequiredFieldValid(data.email)) {
    //   return false;
    // }

    // if (!isRequiredFieldValid(data.password)) {
    //   return false;
    // }
    return true;
  }

  function onSubmit(e) {
    const formData = new FormData(e.target);

    const data = {};
    for (let field of formData) {
      const [key, value] = field;
      data[key] = value;
    }
    if (isFormValid(data)) {
      console.log(data);
    } else {
      console.log("Invalid Form");
    }
  }


	const progress = tweened(0, {
		duration: 1000,
		easing: cubicOut
	});
	let on = true;
	function loop(){
		progress.set((on ? 0.4: 0.9) * 0.5);
		on = !on;
		setTimeout(() => {
			loop();
		}, 2000);
	}
	loop();

</script>

<svelte:head>
  <title>About</title>
  <meta name="description" content="About this app" />
</svelte:head>

<main>
  <form on:submit|preventDefault={onSubmit}>
    <div class="left">
      <div class="headline">
        My new<br/>idea !
      </div>
      <div class="input_cont">
        <label for="title">Title</label> <br />
        <input type="text" id="title" name="title" value="" />
      </div>
      <div class="input_cont">
        <label for="email">Email</label> <br />
        <input type="text" id="email" name="email" value="" />
      </div>
      <div class="submit">
        <button type="submit" class="submit_button">UPLOAD</button>
      </div>

	  <svg class="pointers_left" viewBox="0 0 607 251" fill="none" xmlns="http://www.w3.org/2000/svg">
		<path d="M133.154 154.024L174.749 128.572L187.43 172.79" stroke="#FD5E09" stroke-opacity={$progress} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
		<path d="M3 241.159L50 228.159V274.159" stroke="#09BC8A" stroke-width="6" stroke-opacity={$progress} stroke-miterlimit="3.8637" stroke-linecap="round"/>
		<path d="M79.3077 183.461L126.592 195.385L103.86 235.376" stroke="#48BEFF" stroke-opacity={$progress}  stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
		<path d="M557 97.1588L604 84.1588V130.159" stroke="#48BEFF" stroke-opacity={$progress }  stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
		<path d="M163.165 72.1586L210.229 59.3935L209.999 105.393" stroke="#09BC8A" stroke-opacity={$progress} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
		<path d="M503.169 131.448L548.314 149.884L520.2 186.293" stroke="#09BC8A" stroke-opacity={$progress} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
		<path d="M406.276 63.2065L408.939 111.899L364 102.074" stroke="#48BEFF" stroke-opacity={$progress}  stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
		<path d="M450.115 111.149L473.578 153.898L428.812 164.48" stroke="#FDC959" stroke-opacity={$progress} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
		<path d="M242.007 10.5107L287.658 27.6581L260.588 64.85" stroke="#FDC959" stroke-opacity={$progress} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
		<path d="M341.977 7.64034L356.709 54.1266L310.741 55.8304" stroke="#FD5E09" stroke-opacity={($progress ) % 1} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
		</svg>
		
    </div>
    <div class="right">
		<svg class="pointers_right" viewBox="0 0 667 469" fill="none" xmlns="http://www.w3.org/2000/svg">
			<path d="M557.286 142.001L526.26 179.622L499.858 141.954" stroke="#FD5E09" stroke-opacity={($progress )} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
			<path d="M642.808 62.4274L605 31.6286L642.509 5" stroke="#09BC8A" stroke-opacity={$progress} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
			<path d="M598.595 96.6198L550.007 100.761L558.461 55.5442" stroke="#48BEFF" stroke-opacity={($progress)} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
			<path d="M182.952 368.514L138.868 389.361L131 344.039" stroke="#48BEFF" stroke-opacity={($progress )}  stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
			<path d="M107.925 437.347L65.0002 414.207L96.8325 381" stroke="#FD5E09" stroke-opacity={($progress)} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
			<path d="M555.601 229.178L515.269 256.588L500.491 213.026" stroke="#09BC8A"stroke-opacity={$progress} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
			<path d="M220.158 302L173.22 315.224L173 269.225" stroke="#09BC8A" stroke-opacity={$progress} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
			<path d="M328.688 316.891L310.298 271.727L355.985 266.365" stroke="#48BEFF" stroke-opacity={$progress} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
			<path d="M270.613 282.981L227 261.166L257.801 227" stroke="#FDC959" stroke-opacity={$progress} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
			<path d="M501.162 313.159L452.415 311.83L465.882 267.845" stroke="#FDC959" stroke-opacity={$progress} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
			<path d="M407.588 348.462L378.507 309.317L421.409 292.721" stroke="#FD5E09" stroke-opacity={($progress)} stroke-width="6" stroke-miterlimit="3.8637" stroke-linecap="round"/>
			</svg>
			
      <label for="description" class="description_label">Description</label>

      <textarea
        name="description"
        style="
	  background-image: url({Textarea_bg})"
        id="description"
      />

	 
    </div>
  </form>
</main>

<style>
  * {
    color: white;
    font-size: 1.75rem;
  }
  form {
    max-width: 50rem;
    height: 80vh;
    max-height: 60rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-column-gap: 1rem;
    padding: 0;
    margin: 0 auto;
    /* background-color: cadetblue; */
  }
  form > * {
    width: 100%;
    /* background-color: brown; */
  }
  .left {
    display: flex;
    flex-direction: column;
	position: relative;
  }

  .headline {
    display: grid;
    place-items: center;
    font-size: 5rem;
    flex: 4;
  }

  .input_cont {
    flex: 3;
  }

  .submit {
    flex: 2;
  }

  .submit_button {
    width: calc(100% - 5px);
    height: 5rem;
    font-size: 2rem;
    background-color: #09bc8a;
    border: 3px solid black;
    transition: 200ms;
    box-shadow: 7px 7px #4a665e, 11px 11px black;
  }
  .submit_button:hover {
    transform: scale(1.03);
  }
  .submit_button:active {
    transform: scale(0.98);
  }

  label {
    margin: 2rem 0.5rem;
    font-size: 1.875rem;
  }
  input {
    border: 3px solid white;
    background-color: #000000;
    height: 5rem;
    border-radius: 10px;
    margin: 10px auto;
    padding: 0;
    width: calc(100% - (2 * 3px));
    box-sizing: border-box;
    padding: 1rem;
  }

  .right {
    display: flex;
    flex-direction: column;
	position: relative;
  }

  textarea {
    border: 3px solid white;
    background-color: #00000000;
    border-radius: 10px;
    width: calc(100% - (2 * 3px));
    flex: 1;

    box-sizing: border-box;
    padding: 1rem;
	background-repeat: no-repeat;
	background-size: cover;

  }
  .pointers_left{
	position: absolute;
	bottom: -13rem;
	right: 50%;
	width: 50rem;
  }

  .pointers_right{
	/* background:#5f5f5f; */
	position: absolute;
	width: 50rem;
	top: -5rem;
	right: -48rem;
  }
</style>
<!-- 
	What do we have here!
This is my first entry to the project list. I made an awesome app. Behold! App ... that ... you can eat!!!


You can thank me later, bye!
 -->