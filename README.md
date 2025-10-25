# 🔉 RNNoiseCMake

**RNNoise** is a noise suppression library based on a recurrent neural network.

For more details, kindly visit the [original paper](https://jmvalin.ca/demo/rnnoise/), or the [github repo](https://github.com/xiph/rnnoise/).

This repository is a **CMake** wrapper for the aforementioned project meant for personal use. However, you're free to add this project as a submodule for your own projects. 


## ⚙️ Usage 
You can use this wrapper in two ways. Either by adding it as a submodule, or cloning it on a dependencies folder inside your project.

### By Submodule
First, include the project as a git submodule.
```bash
git submodule add https://cppdecl/RNNoiseCMake.git DepsFolder/RNNoiseCMake/
git submodule update --init --recursive
```
Then somewhere in your CMakeLists.txt
```cmake
add_subdirectory(RNNoiseCMake)
```
Don't forget to link the library.
```cmake
target_link_libraries(${PROJECT_NAME} PRIVATE RNNoise)
```

### By Cloning
Like the first one, clone the repo somewhere in your project.
```bash
git clone https://cppdecl/RNNoiseCMake.git DepsFolder/RNNoiseCMake/
cd DepsFolder/RNNoiseCMake
git submodule update --init --recursive
```
Again, somewhere in your CMakeLists.txt
```cmake
add_subdirectory(RNNoiseCMake)
```
Don't forget to link the library.
```cmake
target_link_libraries(${PROJECT_NAME} PRIVATE RNNoise)
```

## 📥 Reminders

⚠️ Before using RNNoise, make sure that the input audio matches the following formats, otherwise it may cause abnormal
noise cancellation or even crash:

- Sample rate: 48kHz (48000Hz)
- Number of Channels: Mono
- Bit depth: 16-bit integer (s16, i.e. int16_t)

If you are using other audio formats (e.g., 44.1kHz, stereo, float, etc.), use an audio processing library (e.g.,
FFmpeg, SoX, or libsamplerate) for pre-processing conversion first.

## 📃 License

The original [RNNoise](https://github.com/xiph/rnnoise) project is licensed
under the [BSD 3-Clause License](./LICENSE).