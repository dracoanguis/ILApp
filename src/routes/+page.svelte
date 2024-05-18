<script lang="ts">
    import Chat from "$lib/chat.svelte";
    import { Canvas } from "@threlte/core";
    import Model from "$lib/model.svelte";
    import { ButtonGroup, GradientButton } from 'flowbite-svelte';
    import { writable } from 'svelte/store';

    // Create a writable store to hold the model value
    let model = writable(0);

    // Function to handle button clicks
    function setModel(value: number) {
        model.set(value);
    }
</script>

<div class="flex justify-stretch h-full bg-slate-100">
    <div class="half">
        <ButtonGroup class="m-8">
            <GradientButton color="purpleToBlue" on:click={() => setModel(0)}>Femme</GradientButton>
            <GradientButton color="cyanToBlue" on:click={() => setModel(1)}>Homme</GradientButton>
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
