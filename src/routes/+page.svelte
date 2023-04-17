<script>
	/** @type {import('./$types').PageData} */
	import { projects } from '$lib/data/projects';

	// let isPlaying = false;
	// function togglePlay(){
		
	// 	console.log("click");
	// 	isPlaying = !isPlaying;
	// 	console.log(event?.target);
	// }
</script>

<div>
	<div class="container">
		{#each projects as project}
            <div class="projectContainer">
				<div class="project">
					<div class="img" style= {`background: url('http://drive.google.com/uc?export=view&id=${project.image}') no-repeat; background-size: cover; background: "white";`}>
						<div class="svg">	
							

							{#if project.youtube}
								<a href="{project.youtube}" target=”_blank”> 
									<svg class="playBtn" width="72" height="72" viewBox="0 0 72 72" fill="none" xmlns="http://www.w3.org/2000/svg">
										<rect x="0.707107" y="36" width="49.9117" height="49.9117" rx="24.9558" transform="rotate(-45 0.707107 36)" fill="#3A96A3" fill-opacity="0.80" stroke="#ECC977"/>
										<path d="M39 36L35 33V39L39 36Z" fill="#ECC977" stroke="#ECC977" stroke-linejoin="round"/>
									</svg>
								</a>
								{:else}
								<audio  controls>
									<source src="{`https://docs.google.com/uc?export=download&id=${project.link}`}" type="audio/ogg">
									<!-- <source src="horse.mp3" type="audio/mpeg"> -->
									  Your browser does not support the audio element.
								</audio>
							{/if}

							<!-- <button class="button" on:click={togglePlay}>
								{#if isPlaying}
									<svg class="playBtn" width="72" height="72" viewBox="0 0 72 72" fill="none" xmlns="http://www.w3.org/2000/svg">
										<rect x="0.707107" y="36" width="49.9117" height="49.9117" rx="24.9558" transform="rotate(-45 0.707107 36)" fill="#B4B4B4" stroke="#878787"/>
										<path d="M34 39L34 35.8726L34 33" stroke="#878787" stroke-linecap="round"/>
										<path d="M38 39L38 35.8726L38 33" stroke="#878787" stroke-linecap="round"/>
									</svg>
									{:else}
									<svg class="playBtn" width="72" height="72" viewBox="0 0 72 72" fill="none" xmlns="http://www.w3.org/2000/svg">
										<rect x="0.707107" y="36" width="49.9117" height="49.9117" rx="24.9558" transform="rotate(-45 0.707107 36)" fill="#3A96A3" fill-opacity="0.50" stroke="#ECC977"/>
										<path d="M39 36L35 33V39L39 36Z" fill="#ECC977" stroke="#ECC977" stroke-linejoin="round"/>
									</svg>
								{/if}
								
							</button> -->
								



									
							<div class="text">
								<h2>
									<a href={`/project/${project.title}`}>{project.title}</a>
								</h2>
								<p>{project.content}</p>
							</div>
							<div class="pointer">
								<a href={`/project/${project.title}`}>
									<svg class="svgPointer" width="16" height="6" viewBox="0 0 16 6" fill="none" xmlns="http://www.w3.org/2000/svg">
										<path d="M14.6406 2.99992L1.35932 2.99992M1.35932 2.99992L3.62686 0.786368M1.35932 2.99992L3.62686 5.21347" stroke="#878787" stroke-linecap="round"/>
									</svg>
								</a>
							</div>
						</div>
					</div>
				</div>
			</div>
        {:else}
            <div>Bringing the projects...</div>
        {/each}
	</div>
    
</div>


<style>
	audio{
		margin-top: 6rem;
	}
	button{
		all: unset;
	}
	.playBtn{
		margin-top: 3vw;
		scale: 1.5;
	}
	.playBtn:hover{
		scale: 2;
		cursor: pointer;
	}
	.svgPointer rect, path{
		fill: #ffffff2a;
		stroke: #ECC977;
	}
	.container{
		display: flex;
		justify-content: space-around;
		flex-flow: row wrap;
		margin: 5rem 19vw;
		text-align: center;

	}
	.projectContainer{
		width: 33%;
		margin-bottom: 10rem;
	}
	.project{
		margin: 0 2vw;
		height: 15vw;
		border: 2px solid #ECC977;
	}
	.img{
		max-width: 794px;
		height: 100%;
	}
	.svg{
		background: url('https://docs.google.com/uc?export=download&id=1qBsdfRtecC80wb4Y5zmMeJuySzmb30Z5') no-repeat;
		position: relative;
		background-size: cover;
		height: 100%;
		object-fit: fill;
	}
	.text{
		position: absolute;
		bottom: 2vw;
		left: 1vw;
		text-align: start;
	}
	.pointer{
		position: absolute;
		bottom: .8vw;
		right: 1.8vw;
  		transform: scaleX(-1);
	}
	.svgPointer:hover{
		scale: 2.5;
	}
	.svgPointer{
		scale: 2;
	}
	p{
		padding-top: 1rem;
		font-size: 1rem;

	}

	a:hover{
		color: #ECC977;
	}

	
	@media (max-width: 1624px) {
	
		.text{
			position: absolute;
			bottom: 1vw;
			left: 1vw;
			text-align: start;
		}
		.text p{
			display: none;
		}
		.text h2 a{
			font-size: 1rem;
		}
		.pointer{
			bottom: 0;
			right:  0;
			scale: .5;
		}
	
	@media (max-width: 980px) {

		.text h2 a{
			font-size: .7rem;
		}
		.playBtn{
			margin-top: 2vw;
			scale: .9;
		}
	}
}
</style>