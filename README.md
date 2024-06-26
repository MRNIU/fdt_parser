
![GitHub Actions Workflow Status](https://img.shields.io/github/actions/workflow/status/MRNIU/fdt-parser/build.yml)

# 此库已不再维护，如有需要请使用 libfdt(https://git.kernel.org/pub/scm/utils/dtc/dtc.git)

# fdt-parser

解析 dtc 生成的 fdt 数据。

Parse the fdt data generated by the dtc. 

Header only.

## 测试

```shell
cmake --preset build
cd build
make
./bin/fdt_parser_test ../test/riscv64_qemu_virt.dtb
```

## 使用

1. 在 CMake 中添加

    ```cmake
    target_link_libraries(${PROJECT_NAME} PRIVATE
        fdt_parser
    )
    ```

2. 引用头文件

    ```c++
    #include "fdt_parser.hpp"
    ```

    参考 test.cpp


3. 如果要使用 printf/assert，需要自己实现两个函数

    ```c++
    int fdt_parser_printf(const char*, ...);

    bool fdt_parser_assert(bool);
    ```

