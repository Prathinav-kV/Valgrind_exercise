# Valgrind Exercise

## Standard install via command-line
```bash
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
```

Q. What happens when the executable is linked statically? Does Valgrind still detect those same bugs? Why or why not?

Answer:

When the executable is linked statically, Valgrind may not detect the same bugs, particularly those related to dynamic library management. This is because Valgrind relies on instrumentation of shared libraries to monitor memory operations, and static linking may reduce its ability to track certain issues. Additionally, static linking can change the memory layout, potentially altering the behavior of bugs or their visibility.

