<script>
	import Sidebar from './tray/Sidebar.svelte';
	import CardManager from './CardManager.svelte';
	import Part from './Part.svelte';
	import Card from './UI/Card.svelte';
	import Slider from './UI/Slider.svelte';
	import Button from './UI/Button.svelte';
	import ToneIcon from './UI/ToneIcon.svelte';
	import FaceIcon from './UI/FaceIcon.svelte';
	import PartIcon from './UI/PartIcon.svelte';
	import ColorIcon from './UI/ColorIcon.svelte';
	import RotationIcon from './UI/RotationIcon.svelte';
	import BrightnessIcon from './UI/BrightnessIcon.svelte';

	let faceBrightness = 1000;
	let faceContrast = 1000;
	let faceSaturation = 1000;
	let faceWindowX = 20;
	let faceWindowY = 20;
	let partWindowX = 20;
	let partWindowY = 180;
	let showClients = false;

	let currentClient = 2;

	const sounds = [];
	{
		for (let i = 0; i < 4; i++) {
			sounds[i] = new Audio(`/sounds/MONEY${i}.mp3`);
		}
	}

	const swipeSounds = [];
	{
		for (let i = 0; i < 2; i++) {
			swipeSounds[i] = new Audio(`/sounds/FLICK${i}.mp3`);
		}
	}

	const pickClient = (i) => {
		currentClient = i;
		showClients = false;
		const j = Math.floor(Math.random() * 2);
		swipeSounds[j].play();
	};

	const sellPart = (part) => {
		part.isBought = false;
		part.selected = false;
		trays = trays;
		const i = Math.floor(Math.random() * 4);
		sounds[i].play();
	};

	const slideToClients = () => {
		showClients = !showClients
		const j = Math.floor(Math.random() * 2);
		swipeSounds[j].play();
	};

	let trays = [
		[
			{
				isBought: false,
				price: 1234,	image: '/parts/b0.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b00.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b1.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b2.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/b3.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b4.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b5.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b6.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/b7.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b8.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b9.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b11.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/b22.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b33.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b44.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b55.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/b66.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b77.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b88.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/b99.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb0.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb00.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb1.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb2.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb3.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb4.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb5.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb6.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb7.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb11.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb22.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb33.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb44.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb55.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb66.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/bb77.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e0.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e1.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e2.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e3.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e4.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e5.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e6.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e7.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e8.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e9.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e10.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e11.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e12.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e13.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e14.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e15.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e16.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e17.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e18.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e19.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e20.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e21.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e22.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e23.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/e24.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/e25.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/i0.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/i00.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/i1.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/i2.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/i3.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/i4.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/i5.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/i6.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/i7.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/i8.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/i9.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/i11.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/i22.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/i33.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/i44.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/i55.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/i66.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/i77.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/i88.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/i99.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii0.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii00.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii1.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii2.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii3.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii4.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii5.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii6.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii7.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii11.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii22.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii33.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii44.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii55.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii66.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/ii77.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/m0.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/m1.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/m2.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/m3.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/m4.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/m5.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/m6.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/m7.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/m8.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/m9.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/m10.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/m11.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/m12.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/m13.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/m14.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/m15.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/m16.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/n0.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/n1.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/n2.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/n3.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/n4.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/n5.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/n6.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/n7.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/n8.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/n9.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/n10.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/n11.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/n12.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/n13.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/n14.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/n15.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
		[
			{
				isBought: false,
				price: 1234,
				image: '/parts/n16.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
			{
				isBought: false,
				price: 1234,
				image: '/parts/n17.png',
				brightness: 1000,
				contrast: 1000,
				saturation: 1000,
				rotation: 0,
				selected: false,
			},
		],
	];
</script>

<main>
	<div class="main-view" class:main-view--move={showClients}>
		<img class="logo" alt="" src="/logo.png" />
		<div class="backdrop"></div>
		<button class="clients-button" on:click={() => slideToClients()}>
			<img alt="" src="/folder.png" />
		</button>
		<img
			style="filter: brightness({faceBrightness / 1000}) contrast({faceContrast / 1000}) saturate({faceSaturation / 1000});"
			src="/faces/{currentClient}.png"
			class="face"
			alt="" />
		<CardManager>
			{#each trays as tray }
				{#each tray as part }
					{#if part.isBought }
						<Part
							x={(window.innerWidth / 2) + Math.floor(Math.random() * 40) + 1}
							y={(window.innerHeight / 2) + Math.floor(Math.random() * 40) + 1}
							rotation={part.rotation}
							bind:selected={part.selected}>
							<img alt="" src={part.image} style="filter: brightness({part.brightness / 1000}) contrast({part.contrast / 1000}) saturate({part.saturation / 1000});"/>
						</Part>
					{/if}
				{/each}
			{/each}
		</CardManager>
		<CardManager>
			<Card x={faceWindowX} y={faceWindowY}>
				<div class="ui-slider">
					<FaceIcon/>
					<BrightnessIcon/>
					<Slider behavior="expand" bind:value={faceBrightness}/>
				</div>
				<div class="ui-slider">
					<div class="icon-spacer"></div>
					<ToneIcon/>
					<Slider behavior="expand" bind:value={faceContrast}/>
				</div>
				<div class="ui-slider">
					<div class="icon-spacer"></div>
					<ColorIcon/>
					<Slider behavior="expand" bind:value={faceSaturation}/>
				</div>
			</Card>
			{#each trays as tray }
				{#each tray as part }
					{#if part.selected && part.isBought }
						<Card bind:x={partWindowX} bind:y={partWindowY}>
							<div class="ui-slider">
								<PartIcon/>
								<BrightnessIcon/>
								<Slider behavior="expand" bind:value={part.brightness}/>
							</div>
							<div class="ui-slider">
								<div class="icon-spacer"></div>
								<ToneIcon/>
								<Slider behavior="expand" bind:value={part.contrast}/>
							</div>
							<div class="ui-slider">
								<div class="icon-spacer"></div>
								<ColorIcon/>
								<Slider behavior="expand" bind:value={part.saturation}/>
							</div>
							<div class="ui-slider">
								<div class="icon-spacer"></div>
								<RotationIcon/>
								<Slider
									behavior="expand"
									min={-180}
									max={180}
									bind:value={part.rotation}
									playSound={true}
								/>
							</div>
							<div class="buttons">
								<Button variant="danger" click={() => sellPart(part)}>
									Sell Part $
								</Button>
							</div>
						</Card>
					{/if}
				{/each}
			{/each}
		</CardManager>
		<Sidebar bind:trays={trays} />
	</div>
	<div class="clients-view" class:clients-view--open={showClients}>
		<div class="clients-view-wrapper">
			{#each Array(16) as _, i}
				<button class="client-card" on:click={() => pickClient(i)}>
					<img alt="" src="/clients/{i}.png" />
				</button>
			{/each}
		</div>
	</div>
</main>

<style>
	.main-view {
		position: absolute;
		transition: transform ease 500ms;
		width: 100%;
		height: 100%;
	}
	.main-view--move {
		transform: translateY(-100%);
	}
	.client-card {
		height: max-content;
		border-radius: 4px;
		border: none;
		outline: none;
		cursor: pointer;
		transition: transform ease 250ms;
		background: white;
		box-shadow: 0 1px 3px rgba(0,0,0,0.12),
                    0 1px 2px rgba(0,0,0,0.24);
	}
	.client-card:hover {
		transform: scale(1.05);
	}
	.client-card img {
		max-width: 100%;
	}
	.clients-view-wrapper {
		display: grid;
		padding: 24px 128px;
		grid-template-columns: repeat(6, 1fr);
		gap: 32px;
		width: 100%;
	}
	.clients-view {
		position: absolute;
		transition: transform ease 500ms, opacity ease 500ms;
		transform: translateY(100%);
		opacity: 0;
		height: calc(100% - 120px);
		overflow-y: scroll;
		padding-bottom: 16px;
		pointer-events: none;
	}
	.clients-view--open {
		pointer-events: all;
		opacity: 1;
		transform: translateY(120px);
	}
	.clients-button {
		position: fixed;
		bottom: -140px;
		left: -50px;
		background: none;
		outline: none;
		border: none;
		transition: transform ease 250ms;
		cursor: pointer;
	}
	.clients-button img {
		pointer-events: none;
	}
	.clients-button:hover {
		transform: translate(10px, -10px) rotate(2deg);
	}
	.backdrop {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
	}
	.logo {
		position: absolute;
		top: 12px;
		left: 50%;
		width: 300px;
		transform:  translateX(-50%);
	}
	.face {
		position: absolute;
		top: 50%;
		left:  50%;
		transform: translate(-50%, -50%);
		pointer-events: none;
	}

	.buttons {
		margin-top: 16px;
		display: flex;
		justify-content: flex-end;
	}

	.ui-slider {
		display: flex;
		align-items: center;
	}

	.icon-spacer {
		width: 24px;
		margin-right: 8px;
	}

	:global(.ui-slider svg) {
		margin-right: 8px;
	}
</style>