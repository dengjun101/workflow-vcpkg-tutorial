
# Tutorial for workflow and srpc using vcpkg

## On Windows

```bat
md D:\tmp
cd D:\tmp
git clone https://github.com/dengjunplusplus/vcpkg -b workflow
cd vcpkg
.\bootstrap-vcpkg.bat
.\vcpkg.exe install srpc
.\vcpkg.exe integrate install

cd D:\tmp
git clone https://github.com/dengjunplusplus/workflow-vcpkg-tutorial

cd D:\tmp\workflow-vcpkg-tutorial\workflow
cmake  -DCMAKE_TOOLCHAIN_FILE=D:/tmp/vcpkg/scripts/buildsystems/vcpkg.cmake -B build
cmake --build build --config Debug
cmake --build build --config Release

cd D:\tmp\workflow-vcpkg-tutorial\srpc
cmake  -DCMAKE_TOOLCHAIN_FILE=D:/tmp/vcpkg/scripts/buildsystems/vcpkg.cmake -B build
cmake --build build --config Debug
cmake --build build --config Release
```

## On Linux & Mac

```bash
cd /tmp
rm -rf vcpkg
rm -rf workflow-vcpkg-tutorial
git clone https://github.com/dengjunplusplus/vcpkg -b workflow
cd vcpkg
./bootstrap-vcpkg.sh
./vcpkg install srpc
./vcpkg integrate install

cd ..
git clone https://github.com/dengjunplusplus/workflow-vcpkg-tutorial.git
cd workflow-vcpkg-tutorial/workflow
cmake -DCMAKE_TOOLCHAIN_FILE=/tmp/vcpkg/scripts/buildsystems/vcpkg.cmake -B build
cmake --build build --config Debug
cmake --build build --config Release

cd ../srpc
cmake -DCMAKE_TOOLCHAIN_FILE=/tmp/vcpkg/scripts/buildsystems/vcpkg.cmake -B build
cmake --build build --config Debug
cmake --build build --config Release
```
