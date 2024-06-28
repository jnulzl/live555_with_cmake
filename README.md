## live555 CMake Build Supported
**Based on live555 version 2024.6.26**

### Build

- 1、Add your computer arch's  openssl in thirdparty directory if ` -DWITH_OPENSSL=ON`

- 2、CMake build

```shell
>> mkdir build && cd build
## For static libs
>> cmake ../ -DBUILD_SHARED_LIBS=OFF -DWITH_OPENSSL=ON -DLINUX_ARCH=aarch64 -DCMAKE_CXX_COMPILER=/opt/gcc-arm-8.3-2019.03-x86_64-aarch64-linux-gnu/bin/aarch64-linux-gnu-g++-8.3.0 -DCMAKE_C_COMPILER=/opt/gcc-arm-8.3-2019.03-x86_64-aarch64-linux-gnu/bin/aarch64-linux-gnu-gcc-8.3.0 # -DCMAKE_CXX_STANDARD=17

## For shared libs
>> cmake ../ -DBUILD_SHARED_LIBS=ON -DWITH_OPENSSL=ON -DLINUX_ARCH=aarch64 -DCMAKE_CXX_COMPILER=/opt/gcc-arm-8.3-2019.03-x86_64-aarch64-linux-gnu/bin/aarch64-linux-gnu-g++-8.3.0 -DCMAKE_C_COMPILER=/opt/gcc-arm-8.3-2019.03-x86_64-aarch64-linux-gnu/bin/aarch64-linux-gnu-gcc-8.3.0 # -DCMAKE_CXX_STANDARD=17
```
Output libs and exe at *bin/${LINUX_ARCH}*  directory
## For documentation and instructions for building this software,
### see <http://www.live555.com/liveMedia/>
