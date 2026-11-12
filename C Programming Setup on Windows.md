# Method 1 (standalone) :
# C Programming Setup Using MinGW-w64

**Operating System:** Windows 10 / 11  
**Editor:** Visual Studio Code  
**Compiler:** GCC (MinGW-w64)  
**Installation Method:** Standalone WinLibs (Without MSYS2)

---

## Step 1: Download VS Code

Visit:

https://code.visualstudio.com/download

Download and install Visual Studio Code for Windows.

---

## Step 2: Download MinGW-w64

Visit the WinLibs website:

https://winlibs.com/

Choose the latest release with:

- Architecture: x86_64 (64-bit)
- Threads: POSIX
- Runtime: UCRT
- Compiler: GCC
- Package: ZIP archive

**Note:** Choose the latest Win64 UCRT + POSIX build.

---

## Step 3: Extract MinGW-w64

1. Open the downloaded ZIP file.
2. Extract its contents.
3. Move the extracted compiler folder to:

```text
C:\mingw64
```

Your folder structure should contain:

```text
C:\mingw64
    ├── bin
    ├── include
    ├── lib
    └── libexec
```

**Important:** Make sure `gcc.exe` exists inside the `bin` folder.

---

## Step 4: Configure Environment Variables

Add the following folder to Windows PATH:

```text
C:\mingw64\bin
```

### Configuration Steps

1. Search for Environment Variables in Windows.
2. Select Edit the system environment variables.
3. Click Environment Variables.
4. Under User Variables, select Path.
5. Click Edit.
6. Click New.
7. Paste:

```text
C:\mingw64\bin
```

8. Click OK to save all changes.

Close and reopen Command Prompt or VS Code.

---

## Step 5: Verify GCC Installation

Open Command Prompt or VS Code Terminal.

Check GCC:

```bash
gcc --version
```

Check GDB:

```bash
gdb --version
```

If version details appear, the installation is successful.

---

## Step 6: Install C/C++ Extension

1. Open VS Code.
2. Press `Ctrl + Shift + X`.
3. Search for C/C++.
4. Install the Microsoft C/C++ extension.

### Screenshot: C/C++ Extension

![Microsoft C/C++ Extension](https://raw.githubusercontent.com/microsoft/vscode-docs/main/docs/cpp/images/cpp/cpp-extension.png)

---

## Step 7: Create Your First C Program

1. Open VS Code.
2. Create a folder named `C_Programming`.
3. Open the folder in VS Code.
4. Create a new file named `hello.c`.

### Screenshot: Creating a New File

![VS Code New File](https://raw.githubusercontent.com/microsoft/vscode-docs/main/docs/cpp/images/mingw/new-file-button.png)

### Write Your First C Program

```c
#include <stdio.h>

int main()
{
    printf("Hello World!");

    return 0;
}
```

Save the file using `Ctrl + S`.

---

## Step 8: Compile and Run C Program

Open the VS Code terminal:

```text
Ctrl + ~
```

### Compile the Program

```bash
gcc hello.c -o hello
```

### Execute the Program

```bash
.\hello.exe
```

### Expected Output

```text
Hello World!
```

### Screenshot: Program Output in VS Code

![VS Code Terminal Output](https://raw.githubusercontent.com/microsoft/vscode-docs/main/docs/cpp/images/playbutton/helloworld-terminal-output.png)

---

## Step 9: Recommended Folder Structure

```text
C_Programming/
│
├── Day01/
│   ├── hello.c
│   └── introduction.c
│
├── Day02/
│   ├── variables.c
│   └── data_types.c
│
├── Day03/
│   ├── operators.c
│   └── input_output.c
│
└── Projects/
```

---

## Software Summary

| Software | Purpose |
|---|---|
| VS Code | Writing C programs |
| MinGW-w64 | Windows compiler toolchain |
| GCC | Compiling C programs |
| GDB | Debugging C programs |

---

## Official Resources

1. VS Code: https://code.visualstudio.com/
2. WinLibs: https://winlibs.com/
3. MinGW-w64: https://www.mingw-w64.org/
4. VS Code C/C++ Guide: https://code.visualstudio.com/docs/languages/cpp

**Congratulations! Your C Programming Environment Is Ready.**



#################################

# Method 2 (using MSYS2) :

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
