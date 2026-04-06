# KateLSP-Setting

Simple setup guide for using Language Server Protocol (LSP) with Kate Editor.

## C/C++ Setup (clangd)

### 1. Install clangd

Download from:
https://clangd.llvm.org/

Or install via package manager:

Linux / Termux:
pkg install clang

Windows:
Download LLVM and install it.

### 2. Add clangd to PATH

Make sure the "bin" folder is in your environment variables.

Example (Windows):
C:\Program Files\LLVM\bin

Verify installation:
clangd --version

### 3. Configure Kate LSP

Open:
Settings → Configure Kate → LSP Client → User Server Settings

If clangd is not detected automatically, you can add it manually here.

### 4. Test it

Open a .cpp file and type:
`std::`

If autocomplete appears → working

## Optional (Recommended)

Create a compile_commands.json for better IntelliSense.

Generate using CMake:
cmake -DCMAKE_EXPORT_COMPILE_COMMANDS=ON .

You can also use a .clangd file for additional configuration, but it does NOT replace compile_commands.json.

## Notes

* Without compile_commands.json, clangd may have limited understanding of your project
* Works best with CMake projects
