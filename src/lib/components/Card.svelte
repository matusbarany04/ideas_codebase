<script>
  export let data;
//   import Explore from '$lib/images/Explore.svg';

</script>

<div class="card_container">
  <div class="card_header">
    <div style="flex:1" />  
    <svg
      class="header"
      viewBox="0 0 187 26"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path d="M22 0H187V26H0L22 0Z" fill="#48BEFF" />
    </svg>
  </div>
  <div class="card_body">
    <div class="title_cont">
      <p class="title">{data.title}</p>
    </div>
    <p class="desc">{data.description}</p>
    <a class="explore_button" href={"/detail?id=" + data.id}>
        <svg
        width="44"
        height="44"
        viewBox="0 0 44 44"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <g filter="url(#filter0_d_22_92)">
          <path
            d="M7 33H37M37 33V3M37 33L7 3"
            stroke="black"
            stroke-width="5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </g>
        <defs>
          <filter
            id="filter0_d_22_92"
            x="0.5"
            y="0.5"
            width="43"
            height="43"
            filterUnits="userSpaceOnUse"
            color-interpolation-filters="sRGB"
          >
            <feFlood flood-opacity="0" result="BackgroundImageFix" />
            <feColorMatrix
              in="SourceAlpha"
              type="matrix"
              values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"
              result="hardAlpha"
            />
            <feOffset dy="4" />
            <feGaussianBlur stdDeviation="2" />
            <feComposite in2="hardAlpha" operator="out" />
            <feColorMatrix
              type="matrix"
              values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.25 0"
            />
            <feBlend
              mode="normal"
              in2="BackgroundImageFix"
              result="effect1_dropShadow_22_92"
            />
            <feBlend
              mode="normal"
              in="SourceGraphic"
              in2="effect1_dropShadow_22_92"
              result="shape"
            />
          </filter>
        </defs>
      </svg>
      
    </a>
  </div>
</div>

<style>
  * {
    /* border: 1px solid red; */
    color: black;
}
  .card_container {
    display: flex;
    flex-direction: column;

    aspect-ratio: 6/7;
    width: 20rem;
  }

  .card_body {
    position: relative;
    padding: 1rem;
    flex: 10;
    background-color: #48beff;
  }
  .card_header {
    display: flex;
  }
  .header {
    flex: 1;
  }

  .title_cont {
    border: 3px solid black;
    border-radius: 500rem;
  }
  .title {
    font-size: 1.7rem;
    margin: 0.5rem;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    text-align: center;
  }

  .desc {
    font-size: 1.7rem;
    overflow: hidden;
    display: -webkit-box;
    -webkit-line-clamp: 6;
    -webkit-box-orient: vertical;
  }
  .explore_button {
    position: absolute;
    bottom: 0;
    right: 0;
    margin: 1rem;
  }
  .explore_button:hover{
    cursor: pointer;
    transform: scale(1.05);
  }
  .explore_button:active{
    transform: scale(0.95);
  }
</style>
