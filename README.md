# cpp-boilerplate-v2-valgrind_exercise
# Valgrind Exercise

What happens when the executable is linked statically?

Ans: In static linking, an executable contains all the necessary libraries and dependencies within itself. This approach embeds the code directly into the executable file, making it self-sufficient and independent of external shared libraries (such as .so files on Linux) when running. While this increases the file size, it ensures that the executable has everything it needs without relying on separate library files.

Does Valgrind still detect the same bugs?

Yes, Valgrind can still identify the same memory-related issues, such as memory leaks and uninitialized variables, even if the executable is statically linked. Since Valgrind works by analyzing the binary at runtime, it tracks how memory is allocated, accessed, and released regardless of whether the program uses static or dynamic linking. The program's memory management behavior remains consistent, allowing Valgrind to detect the same problems in both cases.

Why or why not?

The way a program handles memory management, such as allocating and freeing memory, remains consistent regardless of whether it’s statically or dynamically linked. Linking doesn’t alter the program’s logic or how memory-related functions operate.

Valgrind's Memcheck tool examines the machine code produced by the compiler and tracks how the program interacts with memory during execution, including allocations, accesses, and releases. Because Memcheck focuses on the program's actual behavior at runtime, it can identify memory-related issues in both statically and dynamically linked executables.

# Standard install via command-line

# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
# To build with debugging information, do:
  cmake -S ./ -B build/ -D CMAKE_BUILD_TYPE=Debug
# Compile and build the project:
  # rebuild only files that are modified since the last build
  cmake --build build/
  # or rebuild everything from scracth
  cmake --build build/ --clean-first
  # to see verbose output, do:
  cmake --build build/ --verbose
# Run program:
  ./build/app/shell-app
# Clean
  cmake --build build/ --target clean
# Clean and start over:
  rm -rf build/
