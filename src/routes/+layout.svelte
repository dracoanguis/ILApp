<script>
	import { NavBrand, NavLi, NavUl, Navbar } from 'flowbite-svelte';
	import '../app.pcss';

	let menu = [
		{name: "Chat", href: "/chat"}
	]

</script>

<Navbar class="bg-purple-700" style="height: 9vh;">
	<NavBrand href="/">
		<p class="text-3xl font-bold text-white">Nom trop stylé++</p>
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