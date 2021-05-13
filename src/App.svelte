<script>
	import PreviewCard from './Preview-card.svelte'
</script>

<main>
	<PreviewCard color="var(--orange)">
		<img slot="icon" src="../images/icon-sedans.svg" alt="sedans icon">
		<h1 slot="header">Sedans</h1>
		<p style="--line-size: 190px;" slot="content">
			Choose a sedans for it's affordabiltiy and excellent fuel economy.
			Ideal for cruising in the city or on your next road trip.
		</p>
		<button slot="callAction">Learn More</button>
	</PreviewCard>

	<PreviewCard color="var(--cyan-100)">
		<img slot="icon" src="../images/icon-suvs.svg" alt="suvs icon">
		<h1 slot="header">Suvs</h1>
		<p style="--line-size: 190px;" slot="content">
			Take an SUV for its spacious interior, power, and versatility.
			Perfect for your next family vacation and off-road adventures.
		</p>
		<button slot="callAction">Learn More</button>
	</PreviewCard>

	<PreviewCard color="var(--cyan-300)">
		<img slot="icon" src="../images/icon-luxury.svg" alt="luxury icon">
		<h1 slot="header">Luxury</h1>
		<p style="--line-size: 190px;" slot="content">
			Cruise in the best car brands without the bloated prices. Enjoy
			the enhanced comfort of luxury rental and arrive <br> in style.
		</p>
		<button slot="callAction">Learn More</button>
	</PreviewCard>
</main>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Big+Shoulders+Display:wght@700&family=Lexend+Deca&display=swap');
	
	:global(:root) {
		--orange: hsl(31, 77%, 52%);
		--cyan-100: hsl(184, 100%, 22%);
		--cyan-300: hsl(179, 100%, 13%);
		--white: hsla(0, 0%, 100%, 0.75);
		--grey: hsl(0, 0%, 95%);

		--deca: 'Lexend Deca', sans-serif;
		--shoulders: 'Big Shoulders Display', cursive;

		background: var(--grey);
	}
	
	:global(body), :global(*) {
		margin: 0;
		padding: 0;
		font-size: 15px;
	}

	:global(body), main { display: grid; }

	main {
		place-self: center;
		place-content: center;
		grid-template: 1fr / repeat(3, 1fr);
		border-radius: 10px;
		overflow: hidden;
	}

	img {
		width: min-content;
		height: min-content;
		background: transparent;
	}

	h1 {
		text-transform: uppercase;
		font-size: 2.5rem;
		font-family: var(--shoulders);
		color: var(--grey);
	}

	p {
		--line-size: 0;
		font-family: var(--deca);
		font-weight: 400;
		font-size: 0.9rem;
		line-height: 1.8;
		inline-size: var(--line-size);
		overflow-wrap: break-word;
		color: var(--white);
	}

	button {
		font-family: var(--deca);
		font-size: 0.9rem;
		/* this var comes Preview-Card.svelte */
		color: var(--color);
		border-radius: 50px;
		--scale: 0.9;
		width: calc(150px * var(--scale));
		height: calc(50px * var(--scale));
		align-self: end;
		transition: background 0.1s ease-in-out, color 0.1s ease-in-out, outline 0.1s ease-in-out;
	}

	button:hover {
		color: white;
		outline: white solid 1px;
		background: transparent;
	}


	@media screen and (max-width: 375px) {
  		main { grid-template: 1fr 1fr 1fr / 1fr; }
		img { scale: 0.9; }
		h1 { font-size: 2rem; }
		p { font-size: 0.8rem; }
		button {
			font-size: 0.8rem; 
			--scale: 0.8; 
		}
	}	
</style>