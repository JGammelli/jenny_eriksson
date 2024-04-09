<script>
  /** @type {import('./$types').PageData} */
  export let data;
  let activeProgramming = true;

  if(!data.isProgram){
    activeProgramming = false;
  }
  function changeRole(){
    console.log("CLICK");
    activeProgramming = !activeProgramming;
  }
</script>

<div class="container">
  <div class="backContainer">
    <a href="/">
      <svg class="backArrow" width="16" height="6" viewBox="0 0 16 6" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M14.6406 2.99992L1.35932 2.99992M1.35932 2.99992L3.62686 0.786368M1.35932 2.99992L3.62686 5.21347" stroke="#878787" stroke-linecap="round"/>
      </svg>
    </a>
  </div>
  <h1>{data.title}</h1>
  <div class="projectContainer">
    <div class="projectItem">
      {#if data.isDesign && data.isProgram}
        <div>
          <div class="roles">
            <div>
              <button id="rolePointer" on:click={changeRole}>
                <p>Programming</p>
                {#if activeProgramming}
                <svg class="pointer"  width="97" height="35" viewBox="0 0 97 15" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M37.1014 1.99998L48.5 13.6221L59.8986 1.99998" stroke="#8E8E8E"/>
                  <path d="M97 1.99998H59.8986" stroke="white" />
                  <rect x="45.3182" y="4.35354" width="5" height="5" transform="rotate(-45 45.3182 4.35354)" fill="#589981"/>
                  <path d="M37.1014 1.99998H0" stroke="white" />
                </svg>
                  {:else}
                    <svg class="pointer" width="98" height="2" viewBox="0 0 98 2" fill="none" xmlns="http://www.w3.org/2000/svg">
                      <path d="M0 1H98" stroke="#8E8E8E"/>
                    </svg>
                {/if}
              </button>
            </div>
            
            <div>
              <button id="rolePointer" on:click={changeRole}>
                <p>Design</p>
                {#if !activeProgramming}
                <svg class="pointer"  width="97" height="35" viewBox="0 0 97 15" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M37.1014 1.99998L48.5 13.6221L59.8986 1.99998" stroke="#8E8E8E"/>
                  <path d="M97 1.99998H59.8986" stroke="white"/>
                  <rect x="45.3182" y="4.35354" width="5" height="5" transform="rotate(-45 45.3182 4.35354)" fill="#589981"/>
                  <path d="M37.1014 1.99998H0" stroke="white"/>
                </svg>
                  {:else}
                    <svg class="pointer"  width="98" height="2" viewBox="0 0 98 2" fill="none" xmlns="http://www.w3.org/2000/svg">
                      <path d="M0 1H98" stroke="#8E8E8E"/>
                    </svg>
                {/if}
              </button>
            </div>
          </div>
        </div>
        {:else}
          {#if data.isDesign && !data.isProgram}
            <svg class="pointer"  width="97" height="35" viewBox="0 0 97 15" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M37.1014 1.99998L48.5 13.6221L59.8986 1.99998" stroke="#8E8E8E"/>
              <path d="M97 1.99998H59.8986" stroke="white" />
              <rect x="45.3182" y="4.35354" width="5" height="5" transform="rotate(-45 45.3182 4.35354)" fill="#589981"/>
              <path d="M37.1014 1.99998H0" stroke="white"/>
            </svg>
          {:else}
            {#if !data.isDesign && data.isProgram}
            <p>Programming</p>
            <svg class="pointer"  width="97" height="35" viewBox="0 0 97 15" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M37.1014 1.99998L48.5 13.6221L59.8986 1.99998" stroke="#8E8E8E"/>
              <path d="M97 1.99998H59.8986" stroke="white" />
              <rect x="45.3182" y="4.35354" width="5" height="5" transform="rotate(-45 45.3182 4.35354)" fill="#589981"/>
              <path d="M37.1014 1.99998H0" stroke="white"/>
            </svg>
            {/if}
        {/if}
      {/if}

      {#if activeProgramming}
        <p class="content">{data.programText}</p>
        {:else}
        <p class="content">{data.designText}</p>
      {/if}
      
    </div>
    <div class="projectItem video">
          {#if data.youtube}
          <a class="playBtn" href="{data.youtube}" target=”_blank”> 
            <svg class="play" width="120" height="120" viewBox="0 0 72 72" fill="none" xmlns="http://www.w3.org/2000/svg">
              <rect x="0.707107" y="36" width="49.9117" height="49.9117" rx="24.9558" transform="rotate(-45 0.707107 36)" fill="#3A96A3" fill-opacity="0.80" stroke="#ECC977"/>
              <path d="M39 36L35 33V39L39 36Z" fill="#ECC977" stroke="#ECC977" stroke-linejoin="round"/>
            </svg>
          </a>
								{:else}
								<audio  controls>
									<source src="{`../src/music/${data.link}`}" type="audio/ogg">
									<!-- <source src="horse.mp3" type="audio/mpeg"> -->
									  Your browser does not support the audio element.
								</audio>
							{/if}
     
       <img src={`../src/images/${data.image}`} alt="image">
    </div>
  </div>
  
</div>
 
<style>
  .play:hover{
   scale: 1.3; 
  }

  .video{
    position: relative;
    min-width: 574px;
    max-width: 725px;
  }
  .playBtn{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  rect{
    fill: #ECE8E1;
  }
  path{
    stroke: #ECC977;
  }
  p{
    line-height: 2;
  }
  .pointer{
    scale: 1.2;
  }
  button {
    all: unset;
    cursor: pointer;
  }
  button:hover {
    color: #ECC977;
  }
  .content{
    margin-top: 2rem;
    margin-bottom: 2rem;
    min-width: 563px;
  }
  .roles{
    display: flex;
    margin-bottom: 1rem;
  }
  .container{
		margin: 5rem 25rem;
		text-align: center;
	}
	.projectContainer{
    display: flex;
    flex-direction: row;
	}
  .projectItem{
		width: 50%;
    margin: 2vw;
		margin-top: 8rem;
  }
  img{
    width: 100%;
    max-width: 750px;
    border: 1px solid #ECC977;
  }
  .backContainer{
    max-width: 1402px;
    text-align: start;
  }
  a{
    text-align: start;
  }
  .backArrow{
    scale: 1.8;
  }
  .projectContainer {
		text-align: center;
	}
  .backArrow:hover{
    scale: 2.5;
  }
  .link:hover{
    color: #ECC977;
  } 
  .link{
    color: #ECC977;
  }
  @media (max-width: 1875px) {
    .projectContainer{
      flex-direction: column;
      width: 100%;
    }
    .container{
      width: 100vw;
      margin: 0rem 0rem;

    }
    img{
      max-width: 100vw;
      margin-top: 2rem;
    }
    .backContainer{
      max-width: 100vw;
    }
    .roles{
      margin-bottom: 0rem;
    }
    .projectItem{
      width: 70%;
      margin: 0vw;
      margin-top: 0rem;
      align-self: center;
    }
    .backArrow{
      scale: 1.8;
    }
    .backContainer{
      max-width: 100%;
      text-align: center;
      margin-bottom: 3rem;
    }
    h1{
      margin-bottom: 2rem;
    }
  }
</style>