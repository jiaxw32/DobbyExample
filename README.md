# DobbyExample

Build and debug Dobby with Xcode

## Build

1. clone code: `git clone git@github.com:jmpews/Dobby.git && cd ./Dobby`
2. edit `CMakeLists.txt` file，set `DOBBY_GENERATE_SHARED` to `OFF`, as follow. If you need dynamic library, you can skip this step.

   ```
   +option(DOBBY_GENERATE_SHARED "Build shared library" OFF)
   ```
3. run command: `mkdir xcode-build && cd ./xcode-build && cmake .. -G Xcode -DCMAKE_OSX_ARCHITECTURES=arm64`
4. open `Dobby.xcodeproj` build，then generate `libdobby.a` lib.

## Debug

1. replace `./DobbyExample/Dobby/libdobby.a` of the project with your generated lib just now.
2. happy debug!

