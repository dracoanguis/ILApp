<script lang="ts">
    import Chat from "$lib/chat.svelte";
    import { Canvas } from "@threlte/core";
    import Model from "$lib/model.svelte";
</script>

<div class="flex justify-stretch h-full bg-slate-100">
    <div class="half">
        <Canvas>
            <Model/>
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