---
title: 'Xenko 1.1 Beta Released'
author: silicon-studio
image_thumb: /images/blog/release-1.1/robot_editor_thumb.jpg
tags: ['Release']
---

Everyone on the Xenko team has been working hard to bring you new features and tools, including the Scene Editor, PBR, and PostFX. We are proud to announce that Xenko 1.1 Beta version is now available for download.

---

[[TOC]]

{% img 'Example Asset' '/images/blog/release-1.1/robot_editor.jpg' %}

## Highlights

<p>Here are the new features on the new and updated version 1.1.0-beta:</p>

<ul>
<li><b>Physically Based Rendering</b> with Layered Material System</li>
<li>A brand <b>new scene editor</b> that is now the central piece of Xenko to assemble your game levels, test the rendering, script your entities.</li>
<li><b>Scene rendering compositor</b>, offering a new way to define precisely how to render scenes in your game, apply post effects...etc.</li>
<li>Easy-to-use and powerful <b>post-effects API</b> coming along many built-in effects (Depth Of Field, Bloom, Lens Flare, Glare, ToneMapping, Vignetting, Film Grain, Antialiasing...)</li>
<li>New implementation of <b>Shadow Mapping</b>, supporting SDSM (Sample Distribution Shadow Maps with adaptive depth splits)</li>
<li><b>Scripting System</b>, to easily add behavior and data to entities</li>
<li>In Visual Studio, when you edit .pdxsl shaders, there is now <b>Error Highlighting</b> and <b>F12 (Go to Definition)</b> to make shader editing as smooth as possible.</li>
<li>A <b>new launcher</b>, that can manage several versions of Xenko SDK side-by-side</li>
</ul>

<p>We have been working to get as many mobile platforms to be included in this release but not all are fully supported yet. Some samples may not work yet so we ask for your patience. The whole team is hard at work to make sure that everything will work on the next update.</p>

<p>Details of upcoming releases will also be posted soon so please keep an eye on this blog!</p>

<p>Release date: 2015/04/28</p>

## New Features

<ul>
<li>Launcher: New <strong>launcher</strong> can now manage several versions of the Xenko SDK</li>
<li>Studio: Introducing a brand new <strong>scene editor</strong></li>
<li>Studio: The scene editor is now the central component of the Studio</li>
<li>Studio: The asset log panel now display logs (errors, etc.) of the seleced assets and their dependencies</li>
<li>Studio: Packages now have properties that can be displayed and edited (to set the default scene and some graphics settings)</li>
<li>Studio: Editor and asset compiler are now <strong>x64</strong> compatible.</li>
<li>Effects: New built-in <strong>post-effects</strong>: depth-of-field, color aberration, light streaks, lens flares, vignetting, film grain (noise)</li>
<li>Engine: New Material System supporting <strong>PBR materials</strong>, multi-layered materials with multiple attributes, including: Tessellation, Displacement, Normal, Diffuse, Specular/Metalness, Transparent, Occlusion/Cavity</li>
<li>Engine: New <strong>rendering pipeline compositor</strong> allowing to compose the rendering of the scene by layers and renderers</li>
<li>Engine: New Ambient and Skybox lighting</li>
<li>Engine: New light culling and object culling</li>
<li>Engine: New implementation of <strong>Shadow Mapping</strong> with support for SDSM (Sample Distribution Shadow Maps with adaptive depth splits)</li>
<li>Engine: New <strong>scripting system</strong>, to easily add behavior and data to entities.</li>
<li>Engine: New <code>ComputeEffectShader</code> class for compute-shader live compilation and dispatching</li>
<li>Engine: New entity background component to add a background in a scene</li>
<li>Engine: New entity UI component to add an UI on entities of the scene.</li>
<li>Graphics: Add a shared 2x2 pixel white texture on the <code>GraphicsDevice</code>  (extension method)</li>
<li>Input: Add the possibility to hide and lock the mouse using <code>LockMousePosition</code> function</li>
<li>Mathematics: New <code>SphericalHarmonics</code> class</li>
<li>Physics: Renamed PhysicsEngine into Simulation, the engine now supports one separate Simulation for each scene.</li>
<li>Assets: New asset type <code>RenderFrameAsset</code></li>
<li>Assets: New asset type <code>ProceduralModelAsset</code></li>
</ul>

## Enhancements

<ul>
<li>Assets: Yaml now uses a shorter qualified name without culture and keytoken.</li>
<li>Assets: Added AssetManager.Reload(), to reload on top of existing object</li>
<li>Assets: During asset compilation, improved logging to always display what asset caused an error</li>
<li>Assets: Assets can now have “compile-time dependencies” (i.e. when a Material layer embeds/uses another material at compile-time)</li>
<li>Assets: Add non-generic versions of Load and LoadAsync methods in the AssetManager</li>
<li>Assets: A Get method that allows to retrieve an already loaded asset without increasing the reference counter</li>
<li>Assets: An Unload method overload that takes an url as parameter instead of a reference.</li>
<li>Assets: Asset merging (reimport) is now more flexible</li>
<li>Assets: Add support for sRGB textures</li>
<li>Assets: Add support for HDR textures</li>
<li>Assets/FBX: Add better support for FBX scene unit and up-axis</li>
<li>Assets/FBX: Automatically generates normal maps if they are not present in a 3d model</li>
<li>Assets/FBX: Do not merge anymore vertices belonging to different smoothing groups</li>
<li>Build: Roslyn is now used to compile serialization code (instead of CodeDom)</li>
<li>Build: Improved logging of asset build</li>
<li>Build: Parallelization of the build has been improved.</li>
<li>Core: “Data” classes don’t exist anymore. Now uses AttachedReferenceManager to directly represent design-time and runtime representation of an object with a single unified runtime class.</li>
<li>Core: Add Collections.PoolListStruct</li>
<li>Studio: If an asset or one of its dependency has a compile error, properly add a failure sticker on top of thumbnail, and details in the asset log</li>
<li>Studio: Inside a scene, entities, components and scripts can reference each others.</li>
<li>Studio: If a script can’t properly be loaded (i.e. due to missing types), be nice and try to keep data as is for next save.</li>
<li>Studio: Reduce number of threads by sharing build system for assets, scene, preview &amp; thumbnails (with priority management)</li>
<li>Studio: Shaders are compiled asynchronously (glowing green effect) and compilation errors will be visible (glowing red effect); various shaders are precompiled for faster startup.</li>
<li>Studio: Improved performance by using binary cloning instead of YAML.</li>
<li>Studio: Many visual improvement of the Studio user interface</li>
<li>Graphics: Add GraphicsDevice.PushState/PopState to save/restore Blend, Rasterizer, Depth states and RenderTargets</li>
<li>Graphics: Add Rasterizer wireframes states</li>
<li>Graphics: Add support for using new UserDefinedAnnotation for Direct3D11 API profiling</li>
<li>Graphics: Add support to generate additional texcoords from an existing vertex buffer in VertexHelper</li>
<li>Graphics: Add possibility to add a back face to the plane geometric primitive</li>
<li>Graphics: Add the possibility to bind TextureCube and Texture3D to the <code>SpriteBatch</code></li>
<li>Effects: Infrastructure for recording shader compilations in a Yaml asset and regenerate shaders on different platforms (no UI yet)</li>
<li>Engine: The local transformation of entity linked with a <code>ModelNodeLinkComponent</code> is now taken in account in final world matrix calculation</li>
<li>Engine: Added <code>ScriptComponent</code> to easily add behavior and data to entities directly inside Xenko Studio</li>
<li>Engine: Materials are defined on Model, but can be overridden in <code>ModelComponent</code></li>
<li>Engine: Add access to the <code>SpriteAnimationSystem</code> from the script context.</li>
<li>Mathematics: Add <code>MathUtil.NextPowerOfTwo</code></li>
<li>Mathematics: Add <code>Vector3</code> operators with floats</li>
<li>Mathematics: Add <code>BoundingSphere.FromPoints</code> from an native buffer with custom vertex stride</li>
<li>Mathematics: Add <code>BoundingBoxExt</code> for intersection between frustum and bounding box</li>
<li>Mathematics: Move all <code>GuillotinePacker</code> implementation copies to a single implem in Mathematics</li>
<li>Mathematics: Fix <code>Color3</code> to <code>Color4</code> implicit operator</li>
<li>Mathematics: Add <code>Color3.ToLinear</code>, <code>Color3.ToSRgb</code>, <code>Color4.ToLinear</code>, <code>Color4.ToSRgb</code> methods</li>
<li>Mathematics: Add swizzle extension methods for vector classes</li>
<li>Mathematics: Add explicit conversion method from <code>Int3</code> to <code>Vector3</code></li>
<li>Mathematics: Add <code>MathUtil.Log2</code> method</li>
<li>Mathematics: Add extension method <code>WithAlpha</code> to <code>Color</code> class. It creates a transparent color from an opaque one</li>
<li>Physics: Added scaling parameter for Convex Hull Shape asset.</li>
<li>Physics: Added LocalRotation in collider shape asset description.</li>
<li>Physics: Removed Sprite workaround, added better default values to shapes.</li>
<li>VisualStudio: Improve highligting and navigation for <code>pdxsl</code> files</li>
<li>VisualStudio: Improve error messages when <code>.cs</code> file generation fails</li>
</ul>

## Issues fixed

<ul>
<li>Assets: On OpenGL ES 3.0+ targets, HDR textures were converted to LDR during asset compilation.</li>
<li>Assets/FBX: Animation containing data for only some of the component the Translation/Rotation/Scale are now correctly imported</li>
<li>Engine: Correctly initialize transformation component rotation to the identity quaternion</li>
<li>Engine: <code>EntityManager.Remove</code> was destroying the hierarchy of the entity</li>
<li>Input: Fix the key down status when the game lose and gain focus under Windows</li>
<li>Input: Correctly translate control/shift/alt keys</li>
<li>Graphics: Implemented <code>BlendStateDescription.Equals()</code> and make a readonly copy of <code>BlendState.Description.RenderTargets</code> (so that user can't modify it). Fixes #139</li>
<li>Graphics: Various improvements and bugfixes to OpenGL renderer</li>
<li>Graphics: Add safeguard to avoid engine crashing when generating extremely big font characters</li>
<li>Graphics: Fix discontinuity problems in geometric primitive UV coordinates</li>
<li>Graphics: Fix crash when creating an unordered  texture array of size greater than one</li>
<li>Graphics: Fix the calculation of <code>Buffer</code>’s element count on DirectX</li>
<li>Mathematics: Matrix.Decompose output now a correct rotation matrix free of reflection</li>
<li>Mathematics: Fix bug in Matrix.Invert when determinant was too small</li>
<li>Mathematics: Fix in <code>Color3.ToRgb</code> method</li>
<li>Mathematics: Fix bug in Gradian property of Angle class</li>
<li>Physics: Fixed PhysicsDebugEffect shader, debug shapes should now render again.</li>
<li>Physics: Fixed issues related to creating collider shape assets in the Game Studio.</li>
<li>Shaders: Add missing <code>GroupMemoryBarrierWithGroupSync</code> keyword to shading language</li>
<li>Shaders: Fix order declaration of the constants and  structures in generated shader</li>
<li>Shaders: Remove generation of key for shader parameters with the <code>groupshared</code> keyword</li>
<li>Studio: Many fixes on the undo/redo stack</li>
<li>Studio: The build log panel gets the focus only once per build</li>
<li>Studio: Fix a crash when undocking the Asset log</li>
<li>Studio: The Studio now have a minimum size at startup</li>
<li>Studio: Some entries in the settings menu were not working</li>
<li>Studio: Fix the sound preview when the source file of the asset has been changed</li>
</ul>

## Breaking changes

<ul>
<li>Android: Android projects should be compiled against Android API v5.0 (only a compile-time requirement, runtime requirement is still Android 2.3+)</li>
<li>Assets: The entity asset has been removed, entities should be created inside a scene.</li>
<li>General: Previous Xenko 1.0.x projects cannot be loaded in this new version</li>
<li>Engine: Deferred lighting was removed. We will later add support for Forward+ and Deferred GBuffer shading</li>
<li>Engine: <code>ScriptSystem.Add</code> has been renamed <code>ScriptSystem.AddTask</code>. <code>Add</code> is now used only to add scripts</li>
<li>Engine: Sprites of <code>SpriteComponents</code> are now rendered in 3D. Their size is defined by the scale of the entity</li>
<li>Engine: UI should be configured via entities and <code>UIComponents</code> and not via the <code>UISystem</code> anymore</li>
<li>Engine: <code>VirtualResolution</code> has been removed from <code>Game</code> and should now be set directly in the <code>UIComponent</code></li>
<li>Engine: Direction of Oz axis have been inversed in the UI to have an RH space</li>
<li>Graphics: ParameterCollection are now grouped together in a ParameterCollectionGroup at creation time. This object can then be used in Effect.Apply().</li>
<li>Physics: Collider Shape Asset and Physics Component have been simplified, their asset version is now not compatible with the old version.</li>
<li>Physics: Debug shape rendering has been replaced by editor gizmos.</li>
<li>Shaders: Previous generated code for <code>pdxfx</code> is broken and must be regenerated</li>
<li>Studio: Changed naming conventions of imported assets.</li>
<li>Studio: The studio and asset compilation process are now running only on 64bits machines</li>
</ul>

## Known Issues

<ul>
<li>Platforms: Shaders can’t compile due to lack of a proper workflow on other platforms than Windows Desktop  (this will be fixed soon)</li>
<li>Platforms: Android and iOS platforms are currently not properly supported (this will be fixed soon).</li>
<li>Platforms: iOS x64 is not yet supported (this will be added soon)</li>
<li>Assets: Reimporting a Model asset (i.e. FBX) might have issues when merging materials</li>
<li>Assets: ModelAsset scaling and orientation works only for .FBX, not other formats supported by Assimp library</li>
<li>Studio: Scripts are not automatically reloaded by the editor. Closing and re-opening it is needed in order to see new scripts.</li>
<li>Studio: Renaming default scene won’t properly update reference. Please set again the reference in project properties.</li>
<li>Studio: DDS images cannot be viewed in the Sprite editor</li>
<li>Studio: Collections in assets properties cannot be edited nor displayed in multi-selection</li>
</ul>

