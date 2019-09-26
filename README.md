# tf2ncnn
 
# 1 安装Protobuf-3.4.0
 下载protobuf-3.4.0：[https://github.com/google/protobuf/archive/v3.4.0.zip](https://github.com/google/protobuf/archive/v3.4.0.zip)
```
> cd <protobuf-root-dir>
> mkdir build-vs2017
> cd build-vs2017
> cmake -G"NMake Makefiles" -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=%cd%/install -Dprotobuf_BUILD_TESTS=OFF -Dprotobuf_MSVC_STATIC_RUNTIME=OFF ../cmake
> nmake
> nmake install
```
 假设安装目录为`<protobuf-3.4.0-dir>`
# 2 编译命令
1. 打开`开始`->`visual studio 2017`->`x64 Native Tools Command Prompt for VS 2017`
2. 输入如下命令：
```
> cd tf2ncnn

> set PROTO_DIR=<protobuf-3.4.0-dir>

> cmake -G"NMake Makefiles" -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=%cd%/install -DProtobuf_INCLUDE_DIR=%PROTO_DIR%/build-vs2017/install/include -DProtobuf_LIBRARIES=%PROTO_DIR%/build-vs2017/install/lib/libprotobuf.lib -DProtobuf_PROTOC_EXECUTABLE=%PROTO_DIR%/build-vs2017/install/bin/protoc.exe  ./src

> nmake
```

# 3 使用
```
> tf2ncnn <your-frozen-pb>.pb ncnn.proto ncnn.bin
```
