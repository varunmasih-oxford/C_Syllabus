
# C Programming Setup on Windows

## 1. Download VS Code
https://code.visualstudio.com/download

## 2. Download MSYS2
https://www.msys2.org/

### MSYS2 Installation Folder
![MSYS2 Installation](https://www.msys2.org/images/install-2-path.png)

## 3. Open MSYS2 UCRT64

![MSYS2 UCRT64 Terminal](https://www.msys2.org/images/install-4-terminal.png)

## 4. Install GCC Compiler

Run:

```bash
pacman -Syu
```

Restart MSYS2 UCRT64 if required.

```bash
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

![GCC Installation](https://code.visualstudio.com/assets/docs/cpp/cpp/cpp-install-MSYS2-toolchain.png)

## 5. Configure PATH

Add this folder to Windows Environment Variables:

```text
C:\msys64\ucrt64\bin
```

Restart the terminal.

## 6. Verify GCC

```bash
gcc --version
```

## 7. Install C/C++ Extension

Search for C/C++ in VS Code Extensions.

![C C++ Extension](https://code.visualstudio.com/assets/docs/cpp/cpp/cpp-extension.png)

## 8. Create hello.c

```c
#include <stdio.h>

int main()
{
    printf("Hello World!");
    return 0;
}
```

## 9. Compile and Run

```bash
gcc hello.c -o hello
.\hello.exe
```

Output:

```text
Hello World!
```

## Official References

- VS Code: https://code.visualstudio.com/docs/cpp/config-mingw
- MSYS2: https://www.msys2.org/
- GCC: https://gcc.gnu.org/
