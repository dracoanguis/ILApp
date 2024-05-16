<script lang="ts">
    import Chat from "$lib/chat.svelte";
    import { Canvas, T} from "@threlte/core";
    import { GLTF, Grid, Gizmo, OrbitControls } from "@threlte/extras";
</script>

<div class="flex justify-stretch h-full bg-slate-100">
    <div class="half">
        <Canvas>
            <Gizmo />
            <T.PerspectiveCamera
              makeDefault
              position={[20, 20, 20]}
              fov={36}
              target={[0, 0, 0]}
            >
              <OrbitControls/>
            </T.PerspectiveCamera>
            <T.AmbientLight intensity={5} color={"red"}/>
            <Grid type={"polar"} maxRadius={5}/>
            <GLTF url={"/female_base_mesh/scene.gltf"} />
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