<script lang="ts">
    import { T } from "@threlte/core";
    import { GLTF, Grid, Gizmo, OrbitControls } from "@threlte/extras";

    export let model = 0;

    let model_path = ["/female_base_mesh/scene.gltf", "/male_base_mesh/scene.gltf"];

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
<T.DirectionalLight position={[4, 10, 4]} color={"lightBlue"} intensity={10} />
<Grid type={"polar"} maxRadius={3} />
<GLTF url="{model_path[model]}" castShadow />
