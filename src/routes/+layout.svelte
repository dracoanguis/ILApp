<script>
	import { NavBrand, NavLi, NavUl, Navbar } from 'flowbite-svelte';
	import '../app.pcss';

	let menu = [
		{name: "Home", href: "/"}
	];

</script>

<svelte:head>
	<title>Ivabot</title>
</svelte:head>

<Navbar class="bg-purple-700" style="max-height: 9vh;">
	<NavBrand href="/">
		<img src="/ivabot.svg" alt="" style="height: 5vh;"/>
		<p class="text-3xl font-bold text-white">IvaBot</p>
	</NavBrand>
	<div class="flex">
		<NavUl>
			{#each menu as {name, href}}
			<NavLi href={href}><p class="text-2xl text-white hover:text-purple-4    00">{name}</p></NavLi>
			{/each}
		</NavUl>
	</div>
</Navbar>

<slot />