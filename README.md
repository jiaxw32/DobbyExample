# DobbyExample

Build and Debug Dobby with Xcode

## Build

1. Clone `Dobby` in the `DobbyExample` directory.

   ```bash
   git clone git@github.com:jmpews/Dobby.git && cd ./Dobby
   ```
2. Edit `CMakeLists.txt` file，set `DOBBY_GENERATE_SHARED` to `OFF`, as follow. If you need dynamic library, you can skip this step.

   ```cmake
   +option(DOBBY_GENERATE_SHARED "Build shared library" OFF)
   ```
3. Run the cmake command to generate xcode project

   ```bash
   mkdir xcode-build && cd ./xcode-build && cmake .. -G Xcode -DCMAKE_OSX_ARCHITECTURES=arm64
   ```
4. Open `Dobby.xcodeproj`, select the `dobby` target, then build, generate `libdobby.a` lib.
5. Run the following command to copy the dobby lib and header file.

   ```bash
   cp ./Dobby/xcode-build/build/Debug/libdobby.a ./Dobby/include/dobby.h ./DobbyExample/Dobby
   ```
6. HAPPY DEBUG!

