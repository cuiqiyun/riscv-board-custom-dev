# RuyiSDK 示例 01：Hello World

## Hello World (GCC版)

创建并激活ruyi虚拟环境（GCC）

```
ruyi venv -t toolchain/gnu-plct manual venv-gnu-plct
. ~/venv-gnu-plct/bin/ruyi-activate
```



验证GCC版本

```
riscv64-plct-linux-gnu-gcc -v
```



编译并运行Hello World（GCC）

```
cat << EOF > hello.c
#include <stdio.h>
 
int main() {
    printf("Hello, World!\n");
    return 0;
}
EOF
riscv64-plct-linux-gnu-gcc hello.c -o hello-gcc
./hello-gcc
```

退出ruyi GCC虚拟环境

```
cd ..; ruyi-deactivate
```



## Hello World (LLVM版)

创建并激活ruyi虚拟环境（LLVM）

```
ruyi venv -t toolchain/llvm-plct manual --sysroot-from gnu-plct venv-llvm-plct
. ~/venv-llvm-plct/bin/ruyi-activate
```



验证LLVM版本

```
clang -v
```



编译并运行Hello World（LLVM）

```
clang hello.c -o hello-llvm; ./hello-llvm
```



退出ruyi GCC虚拟环境

```
cd ..; ruyi-deactivate
```

