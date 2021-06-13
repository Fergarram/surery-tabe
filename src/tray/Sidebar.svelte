<script>
	export let trays;

	const buyItem = (part) => {
		part.isBought = true;
		// Reactivity
		trays = trays;
		const i = Math.floor(Math.random() * 4);
		sounds[i].play();
	};

	const sounds = [];
	for (let i = 0; i < 4; i++) {
		sounds[i] = new Audio(`/sounds/MONEY${i}.mp3`);
	}

	const scrollSound = new Audio('/sounds/SLIDE.mp3');

	const playSlideSound = () => {
		scrollSound.play();
	};
</script>

<div on:scroll={playSlideSound} class="sidebar sidebar-1">
	{#each trays as tray, i }
		{#if i >= 22 }
			<div class="tray">
				{#each tray as part }
					<button class:hide={part.isBought} on:click={() => buyItem(part)}>
						<img alt="" src={part.image} />
					</button>
				{/each}
			</div>
		{/if}
	{/each}
</div>
<div on:scroll={playSlideSound} class="sidebar">
	{#each trays as tray, i }
		{#if i < 22 }
			<div class="tray">
				{#each tray as part }
					<button class:hide={part.isBought} on:click={() => buyItem(part)}>
						<img alt="" src={part.image} />
					</button>
				{/each}
			</div>
		{/if}
	{/each}
</div>


<style>
	.sidebar {
		position: fixed;
		top: 0;
		right: 0;
		width: 165px;
		height: 100%;
		overflow-y: scroll;
	}
	.sidebar-1 {
		right: 165px;
	}
	.tray {
		display: flex;
		/*flex-direction: column;*/
		flex-wrap: wrap;
		align-items: center;
		justify-content: center;
		padding: 16px;
		width: 100%;
		height: 229px;
		background-image: url('/tray.png');
	}

	.hide {
		opacity: 0;
		pointer-events: none;
	}

	button {
		cursor: pointer;
		background: none;
		outline: none;
		border: none;
		transition-property: filter, transform;
		transition-duration: 150ms;
		transition-timing-function: ease;
	}

	button img {
		pointer-events: none;
	}

	button:hover {
		filter:  brightness(0.7);
	}

	button:active {
		transform: scale(1.05);
	}
</style>