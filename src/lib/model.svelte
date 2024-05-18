<script lang="ts">
    import { Canvas, T } from "@threlte/core";
    import { GLTF, Grid, Gizmo, OrbitControls } from "@threlte/extras";
    import { onDestroy } from 'svelte';
    import { get } from 'svelte/store';
    import type { Writable } from 'svelte/store';

    export let model: Writable<number>;

    let model_path = ["/female_base_mesh/scene.gltf", "/male_base_mesh/scene.gltf"];
    let modelIndex = 0; 

    // Subscribe to the model store
    const unsubscribe = model.subscribe(value => {
        modelIndex = value;
    });

    // Cleanup on component destroy
    onDestroy(() => {
        unsubscribe();
    });
</script>

<Gizmo />
<T.PerspectiveCamera
  makeDefault
  position={[-2, 10, -20]}
  fov={36}
  target={[0, 5, 0]}
  zoom={2.5}
>
  <OrbitControls autoRotate enableDamping />
</T.PerspectiveCamera>
<T.AmbientLight intensity={3} color={"lightBlue"} />
<T.DirectionalLight position={[4, 10, 4]} color={"lightBlue"} intensity={20} />
<Grid type={"polar"} maxRadius={3} />
<GLTF url="{model_path[modelIndex]}" castShadow />
