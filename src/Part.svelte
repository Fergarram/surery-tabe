<script>
	import { onMount, getContext } from 'svelte';
	import { makeid } from './utils.js';

	export let x = 0;
	export let y = 0;
	export let rotation = 0;
	export let selected = false;

	let card;
	let cardId = makeid();
	const { addCard, moveCard, addListener, getStack } = getContext('cardStack');

	let cardIndex = addCard(cardId);
	addListener(() => {
		cardIndex = getStack().indexOf(cardId);
		card.style.zIndex = cardIndex;
	});

	let isDragging = false;
	let isTyping = false;
	let deltaX = 0, deltaY = 0, mouseX = 0, mouseY = 0;
	let mouseIn = false;
	let windowWidth = window.innerWidth;
	let windowHeight = window.innerHeight;

	onMount(() => {
		card.onmousedown = dragMouseDown;
		card.style.transform = `translate3d(${x}px, ${y}px, 0)`;
		card.addEventListener('mouseenter', () => {
			mouseIn = true;
		});
		card.addEventListener('mouseout', () => {
			mouseIn = false;
		});
		card.addEventListener('click', () => {
			selected = true;
		});
		document.querySelector('.backdrop').addEventListener('mouseup', () => {
			if (!mouseIn) {
				selected = false;
			}
		});
		window.addEventListener( 'resize', () => {
			const xx = (window.innerWidth * x) / windowWidth;
			const yy = (window.innerHeight * y) / windowHeight;
			card.style.transform = `translate3d(${xx}px, ${yy}px, 0)`;
		});
	});

	const setPointerEventsFor = (element, option) => {
		element.style.pointerEvents = option;
	};

	const sounds = [];
	for (let i = 0; i < 6; i++) {
		sounds[i] = new Audio(`/sounds/CLICK${i}.mp3`);
	}

	const dragMouseDown = (e) => {
		let isDraggable = e.target.getAttribute('non-draggable') === null;

		mouseX = e.clientX;
		mouseY = e.clientY;

		const i = Math.floor(Math.random() * 6);
		sounds[i].play();

		moveCard(cardId);

		document.onmousemove = (e) => {
			if (isDraggable) {
				deltaX = mouseX - (e.clientX);
				deltaY = mouseY - (e.clientY);

				mouseX = e.clientX;
				mouseY = e.clientY;

				let rect = card.getBoundingClientRect();
				x = (rect.left - deltaX);
				y = (rect.top - deltaY);

				card.style.transform = `translate3d(${x}px, ${y}px, 0)`;
				isDragging = true;
				setPointerEventsFor(card, "none");
			}

		}

		document.onmouseup = (e) => {
			isDragging = false;
			setPointerEventsFor(card, "initial")
			document.onmousemove = null
			document.onmouseup = null
			selected = true;
			const i = Math.floor(Math.random() * 4);
			sounds[i].play();
		}
	}
</script>

<div
	bind:this={card}
	class="draggable"
	key={cardId}>
	<div
		class="card"
		class:card--selected={selected}
		style="transform: rotate({rotation}deg);"
		class:card--drag={isDragging}>
		<slot></slot>
	</div>
</div>

<style>
	.draggable {
		position: absolute;
		left: 0;
		top: 0;
        cursor: grab;
	}
	.card {
		border: 3px dashed transparent;
		border-radius: 1000px;
		width: fit-content;
        cursor: grab;
	}
	.card--selected {
		border: 3px dashed black;
	}
	:global(.card img) {
		pointer-events: none;
	}
</style>