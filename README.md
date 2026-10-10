# Motion Studio

I've put Motion Studio together to make NVIDIA's Kimodo easier to install and use on Windows. Type the movement you're after, generate it on your own PC, then preview it on a Mixamo character and export it as a GLB.

Use it to try out a movement, block out a sequence or get a first pass to work from in Blender.

[Download Motion Studio 1.2.1 for Windows](https://github.com/ZURAVFX/Motion-Studio/releases/download/v1.2.1/Motion-Studio-Setup-1.2.1.exe)

The installer is 11.9 MB and includes the CPU and Vulkan runtimes. You don't need to install Python, Go, C++ build tools or the Vulkan SDK. Model files download separately, and the app shows the size before you start.

You can add prompt segments to build a sequence, adjust the frames, steps and seed, and keep different takes to come back to later. There are four SOMA/G1 motion models and six text encoders to choose from. Installed files are reused and interrupted downloads can resume.

Import a Mixamo FBX or GLB character to preview the motion on your own mesh. The character export includes the mesh, its Mixamo rig and the animation together, at 30 fps. You can also export the original model skeleton on its own. Your chosen character is remembered across app windows and restarts.

![Motion Studio preview](docs/Motion-Studio-Preview.jpg)

The preview above uses the included fallback mannequin. Imported characters keep their own proportions, bone names and skin weights.

Use the small x beside a saved motion to hide it, or Clear preview to empty the viewport. Both keep the files on disk. Restore hidden motions brings them back.

To get started, run the installer and choose SOMA RP + Q8_0 in the model library. A fresh download of that pair is 9.28 GB (8.65 GiB), so allow at least 12 GB of free disk space. Then write a prompt and press Generate motion.

Generation runs on your CPU or a compatible Vulkan graphics card. Once the models are downloaded, it works offline. Your prompts, characters and generated motions stay on your computer.

Windows 11 x64 with AVX2 is required. ARM Windows isn't supported in this build. At least 16 GB RAM is recommended for Q8_0, and speed depends on your hardware and settings. The installer is unsigned, so Windows may show an unknown-publisher warning.

Treat the output as a starting point. Some movements will need cleaning up, and the model doesn't generate detailed finger animation. SOMA is the better fit for human characters; G1 motion is adapted from a robot rig.

Character FBXs need embedded textures and GLBs need to be self-contained. See the [user guide](docs/Motion-Studio-Team-Guide.txt) for import limits, Blender setup and the full list of model sizes. Separately licensed SMPL-X research models can be imported locally; they aren't included in the downloads.

This public repository contains the Windows installer and documentation. Application source is maintained privately and isn't included here. GitHub's automatic source archives contain the documentation, not the application source.

Built around NVIDIA Kimodo and [kimodo.cpp](https://github.com/localai-org/kimodo.cpp), with [GGML](https://github.com/ggml-org/ggml) and [Three.js](https://threejs.org/). The installer, model library, character preview and export tools are additions to the upstream project. Built with Meta Llama 3.

The engine, models and other components have their own licences. Full [third-party notices](THIRD-PARTY-NOTICES/) are included with the installer, along with the separate NVIDIA and Meta terms. No model weights are bundled.
