<script>
    import { page } from '$app/stores'
</script>

<div class="container">
    <div class="header">
        <h1>Jenny Eriksson</h1>
        <p class="smalTxt">Programmer and Musician</p>
    </div>
    <div class="navigator">
        <nav>
            <div class="navPointer">
                {#if $page.url.toString() === 'https://jennyeriksson.netlify.app/about'}
                    <svg width="1264" height="200" viewBox="0 0 1264 200" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M1182.12 58.9105C1189.24 22.2523 1272.01 30.052 1247.5 75.3697C1220.48 125.335 1049.06 126.5 1010 126.5" stroke="white"/>
                        <path d="M81.8833 59.0408C74.7557 22.3826 -8.00589 30.1823 16.4999 75.5C43.5192 125.466 214.936 126.5 254 126.5" stroke="white"/>
                        <line x1="758" y1="126.5" x2="1010" y2="126.5" stroke="white"/>
                        <line x1="506" y1="126.5" x2="758" y2="126.5" stroke="white"/>
                        <line x1="254" y1="126.5" x2="368" y2="126.5" stroke="white"/>
                        <line x1="393" y1="126.5" x2="506" y2="126.5" stroke="white"/>
                        <path d="M392.5 127C392.5 133.332 387.147 138.5 380.5 138.5C373.853 138.5 368.5 133.332 368.5 127C368.5 120.668 373.853 115.5 380.5 115.5C387.147 115.5 392.5 120.668 392.5 127Z" stroke="white"/>
                        <circle cx="380.5" cy="146.5" r="4" stroke="white"/>
                    </svg> 
                    {:else}
                        {#if $page.url.toString() === 'https://jennyeriksson.netlify.app/contact'}                           
                            <svg width="1264" height="200" viewBox="0 0 1264 200" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M1182.12 58.9105C1189.24 22.2523 1272.01 30.052 1247.5 75.3697C1220.48 125.335 1049.06 126.5 1010 126.5" stroke="white"/>
                                <path d="M81.8833 59.0408C74.7557 22.3826 -8.00589 30.1823 16.4999 75.5C43.5192 125.466 214.936 126.5 254 126.5" stroke="white"/>
                                <line x1="254" y1="126.5" x2="506" y2="126.5" stroke="white"/>
                                <line x1="506" y1="126.5" x2="758" y2="126.5" stroke="white"/>
                                <line x1="758" y1="126.5" x2="872" y2="126.5" stroke="white"/>
                                <line x1="897" y1="126.5" x2="1010" y2="126.5" stroke="white"/>
                                <path d="M896.5 127C896.5 133.332 891.147 138.5 884.5 138.5C877.853 138.5 872.5 133.332 872.5 127C872.5 120.668 877.853 115.5 884.5 115.5C891.147 115.5 896.5 120.668 896.5 127Z" stroke="white"/>
                                <circle cx="884.5" cy="146.5" r="4" stroke="white"/>
                            </svg>
  
                    {:else}
                        <svg width="1264" height="200" viewBox="0 0 1264 200" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M1182.12 58.9105C1189.24 22.2523 1272.01 30.052 1247.5 75.3697C1220.48 125.335 1049.06 126.5 1010 126.5" stroke="white"/>
                            <path d="M81.8833 59.0408C74.7557 22.3826 -8.00589 30.1823 16.4999 75.5C43.5192 125.466 214.936 126.5 254 126.5" stroke="white"/>
                            <line x1="254" y1="126.5" x2="506" y2="126.5" stroke="white"/>
                            <line x1="758" y1="126.5" x2="1010" y2="126.5" stroke="white"/>
                            <line x1="506" y1="126.5" x2="620" y2="126.5" stroke="white"/>
                            <line x1="645" y1="126.5" x2="758" y2="126.5" stroke="white"/>
                            <path d="M644.5 127C644.5 133.332 639.147 138.5 632.5 138.5C625.853 138.5 620.5 133.332 620.5 127C620.5 120.668 625.853 115.5 632.5 115.5C639.147 115.5 644.5 120.668 644.5 127Z" stroke="white"/>
                            <circle cx="632.5" cy="146.5" r="4" stroke="white"/>
                        </svg>
                    {/if}
                {/if}                   
            </div>
            <ul>
                <li><a href="/about" style={`color:${($page.url.toString() === 'https://jennyeriksson.netlify.app/about') ? '#ECC977' : ''}`}>ABOUT</a></li>
                <li><a href="/" style={`color:${($page.url.toString() === 'https://jennyeriksson.netlify.app/') ? '#ECC977' : ''}`}>PORTFOLIO</a></li>
                <li><a href="/contact" style={`color:${($page.url.toString() === 'https://jennyeriksson.netlify.app/contact') ? '#ECC977' : ''}`}>CONTACT</a></li>
            </ul>
        </nav>
    </div>
<slot/>

</div>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@100&display=swap');
    
  /* Pointer svg */
    path, line{
        stroke: #ffffff;
    }
    /* .pointer{
        stroke: #ECE8E1;
    } */
    svg{
        margin-top: -3.5rem;
    }

    a:hover{
        color: #ECC977;
    }
    .container {
		text-align: center;
	}
    .navPointer{
        height: 7rem;
    }
    .header{
        margin-top: 5rem;
    }
    h1{
        font-size: 3rem;
        color: #ECE8E1;
	}
    li{
        width: 252px;
        font-size: 1.5rem;
    }
    ul{
        width: 756px;
        height: 8rem;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
    }
    .smalTxt{
        font-size: 1rem;
        margin-top: 1rem;
        letter-spacing: .4rem;
        color: #ECC977;
    }
    :global(a){
		text-decoration: none;
		color: #ECE8E1;
	}
	:global(body){
		background-color: #459BA8;
		color: #ECE8E1;
        background: url('../images/background.jpg') no-repeat;
        background-size: cover;

	}
	:global(*){
		margin: 0 auto;
		padding: 0;
        letter-spacing: 1px;
		font-family: 'Josefin Sans', sans-serif;
        font-weight: bold;
    }
	:global(li){
		list-style-type: none;
	}
    :global(p, a){
		font-size: 1.2rem;
	}
    @media (max-width: 1024px) {

        .container{
            width: 100vw;
        }
        ul{
            width: 100vw;
            height: 5rem;
        }
        svg{
            width: 100vw !important;
        }
        }
        @media (max-width: 780px) {

        :global(a, p){
            font-size: .7rem;
        }
        :global(body){
            height: 100%;
	    }
    }
</style>

