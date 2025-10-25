Voxel Car — Run in Chrome

This is a minimal, single-file voxel car prototype that runs directly in the browser (Chrome recommended).

How to run

- Open `index.html` in Chrome (double-click the file or use "Open File" in Chrome).
- For better stability or if your browser restricts local file loading, serve the folder with a quick static server, for example using Python from PowerShell:

How to run (immediately)

- The project now contains a file-friendly single-file build. You can open `index.html` directly in Chrome by double-clicking it. It no longer requires module imports or a local server.

Optional: if you prefer serving over HTTP (useful for development), run a simple server from PowerShell:

```powershell
# from inside the project folder
python -m http.server 8000
# then open http://localhost:8000 in Chrome
```

Controls

- W / S : accelerate / brake
- A / D : steer left / right
- Space : handbrake (not fully implemented)
- Left Click : remove a block
- Shift + Left Click : place a block adjacent to the clicked face

Notes and next steps

- This prototype uses plain Three.js (via CDN) and no external physics engine. Car movement is kinematic and simple.
- TODOs: add collision response, smoother vehicle physics, improved voxel performance (instancing / greedy meshing), saving/loading world, first/third-person toggles, lighting/day-night, and multiplayer.
 - Updated version includes realistic vehicle physics using cannon-es (RaycastVehicle), instanced voxel rendering for much better performance on larger worlds, and local save/load using localStorage.

What's included now (updated)
- `index.html` — module-based single-file app that imports Three.js and cannon-es from CDN.
- Smooth heightmap terrain generated with Simplex noise (mountains and hills).
- Road carving: a drivable road loop carved into the heightmap and a visual asphalt strip.
- CANNON Heightfield is used for accurate terrain collisions with the vehicle.
- Tuned RaycastVehicle physics for better driving feel.
- Improved visuals: terrain texture, normal calculations, better lighting.

Controls
- W / S : accelerate / brake
- A / D : steer left / right
- Space : handbrake
- Left Click : (previously used for voxel editing) — now reserved for future interactions

Notes and next steps
- The world uses a heightfield-based terrain; if you still want editable voxels (place/remove blocks), I can add a hybrid system that lets the player edit nearby voxels and updates a collision mesh. That is more complex but doable.
- For higher-fidelity visuals we can add PBR materials, a skybox, ambient occlusion, and better textures.
- If you want a larger world, I can add chunking and LOD so performance stays high.

How to run
- Open `index.html` in Chrome. If Chrome blocks local module loading, run a simple static server from PowerShell in the project folder:

```powershell
# from inside C:\Users\Lenovo\Desktop\LENOVO ATKK\car game
python -m http.server 8000
# then open http://localhost:8000 in Chrome
```

Tell me which visual or physics tweaks you want next (more realistic suspension, better tire friction, PBR materials, day/night cycle, or re-add voxel editing). I'll implement the next step and validate in Chrome.

Controls
- W / S : accelerate / brake
- A / D : steer left / right
- Space : handbrake
- Left Click : remove a voxel block
- Shift + Left Click : place a block adjacent to the clicked face

Notes and next steps
- Performance: instancing helps significantly; for much larger worlds we can add chunking and greedy meshing.
- Physics tuning: the vehicle parameters are conservative; I can tune mass, suspension, friction, and braking to match arcade vs realistic behavior.
- Save/Load: stored in localStorage under key `voxel_world`. I can add import/export buttons (download JSON) if you want.

If you'd like, I can now:
- Add chunking/streaming to expand the world further and keep performance stable.
- Add greedy meshing or merged geometry for non-cubic blocks.
- Add export/import files for saves and autosave.
- Package as a desktop app (Electron / Tauri) or deploy to GitHub Pages.

If you want I can:
- Add better vehicle physics using a physics engine (cannon-es or ammo) and package as a desktop app.
- Expand terrain size and implement chunking/instanced meshes for performance.
- Add UI polish and mobile touch controls.

Tell me which of these you'd like next.

