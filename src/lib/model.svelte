<script lang="ts">
    import { Canvas, T} from "@threlte/core";
    import { GLTF, Grid, Gizmo, OrbitControls } from "@threlte/extras";
</script>

<Gizmo />
<T.PerspectiveCamera
  makeDefault
  position={[-2, 10, -20]}
  fov={36}
  target={[0, 5, 0]}
  zoom={2.5}
>
  <OrbitControls autoRotate enableDamping/>
</T.PerspectiveCamera>
<T.AmbientLight intensity={3} />
<T.DirectionalLight position={[4, 10, 4]} color={"blue"} intensity={20}/>
<Grid type={"polar"} maxRadius={3}/>
<GLTF url={"/female_base_mesh/scene.gltf"} castShadow/>