# Vulkan Tutorial

This project is a Vulkan tutorial application structured as a reusable library. It demonstrates the setup and rendering process using the Vulkan API, along with window management via GLFW.

**IMPORTANT:** This project has been refactored to be built as a shared library instead of an executable. Please refer to the `CMakeLists.txt` for details on how to build and link against this library in your own projects. We do not provide 3d model loading.

## Dependencies

**Needed on your system:**
- A C++17 compatible compiler
- CMake (version 3.14 or higher)
- Vulkan SDK

**Automatically fetched:**
- GLFW (for window management)
- GLM (for mathematics)
- stb_image (for image loading)

## Implementation Details

The main application logic is encapsulated in the `AApp` class, which handles Vulkan initialization, rendering, and cleanup. Key features include:

- Vulkan instance creation and setup
- Debug messenger configuration
- Surface creation for window rendering
- Multisampling support
- Extension management

### How to Use

1. Clone the repository to your local machine.
2. Use CMake to configure and build the project as a shared library.
3. Link against the generated library in your own Vulkan applications.
4. Include the necessary headers from the `headers` directory to access the `AApp` class and its functionalities.
5. Implement your own main function to create an instance of `AApp`, initialize it, and `run()` the main loop.
    - The inherited class should fill the `_appName`, `_engineName`, `_appVersion`, and `_engineVersion` attributes before calling `initVulkan()`.
    - You should also set the `TEXTURE_PATH` variable to point to your texture resources. (It natively manage only one texture.)
    - **Optionnally**, override methods to customize behavior: for example, if you want to manage multiple textures and models you should override relevant methods (`createTextureImage()`, etc.).
6. Build and run your application.
