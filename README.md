# tf2ncnn

# 编译流程
# 1 安装Protobuf-3.4.0
 假设安装目录为`<protobuf-3.4.0-dir>`
# 2 编译命令
1. 打开`开始`->`visual studio 2017`->`x64 Native Tools Command Prompt for VS 2017`
2. 输入如下命令：
> set PROTO_DIR=<protobuf-3.4.0-dir>
> cmake -G"NMake Makefiles" -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=%cd%/install -DProtobuf_INCLUDE_DIR=%PROTO_DIR%/build-vs2017/install/include -DProtobuf_LIBRARIES=%PROTO_DIR%/build-vs2017/install/lib/libprotobuf.lib -DProtobuf_PROTOC_EXECUTABLE=%PROTO_DIR%/build-vs2017/install/bin/protoc.exe  ./src
> nmake
