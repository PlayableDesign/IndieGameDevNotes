# Unity 2020.3 Project Setup: 2D Universal Render Pipeline (URP)

Create a standard empty 2D project, which by default is configured to use the built-in render pipeline.

* Import the Package

```
Package Manager > Unity Registry and install the latest version of "Universal RP"
```

* Add Project Assets

```
Project > Assets > Right-Click > Create > Rendering > Univeral Render Pipeline > Pipeline Asset (Forward Renderer)
Project > Assets > Right-Click > Create > Rendering > Univeral Render Pipeline > 2D Renderer (Experimental)
Project > Assets > Select "New 2D Renderer Data" and set Transparency Sort Mode if needed (optional)
Project > Assets > Select "UniversalRenderPipelineAsset" > Inspector > Renderer List > Drag and drop "New 2D Renderer Data" here
Project > Assets > Select "UniversalRenderPipelineAsset" > Inspector > Quality > Anti Aliasing (MSAA) > change to 4X (optional)
```

* Configure Project Settings

```
Edit > Project Settings > Graphics > Scriptable Render Pipeline Settings Select "UniversalRenderPipelineAsset"
Edit > Project Settings > Quality > Rendering > Select "UniversalRenderPipelineAsset"
```

* Upgrade Project Materials

```
Edit > Render Pipeline > Universal Render Pipeline > 2D Renderer > Upgrade Project to 2D Renderer (Experimental)
```

If you import other packages that contain materials, you may need to repeat the last step again to upgrade those materials to URP.
