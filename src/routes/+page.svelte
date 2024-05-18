<script lang="ts">
    import Chat from "$lib/chat.svelte";
    import { Canvas } from "@threlte/core";
    import Model from "$lib/model.svelte";
    import { ButtonGroup, GradientButton } from 'flowbite-svelte';
    import { writable } from 'svelte/store';

    let model = writable(0);

    function setModel(value: number) {
        model.set(value);
    }
</script>

<div class="flex justify-stretch h-full bg-slate-100 relative">
    <div class="half relative">
        <ButtonGroup class="absolute top-5 left-5">
            <GradientButton shadow color="purple" on:click={() => setModel(0)}>Femme</GradientButton>
            <GradientButton shadow color="purple" on:click={() => setModel(1)}>Homme</GradientButton>
        </ButtonGroup>
        <Canvas>
            <Model {model}/>
        </Canvas>
    </div>
    <div class="half flex justify-center">
        <Chat />
    </div>
</div>

<style>
    .half {
        width: 50vw;
        height: 91vh;
    }
</style>
