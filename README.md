# Valgrind Exercise

## Standard install via command-line
```bash
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
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

The valgrind_output.txt file contains the valgrind output.

Extra Credit answers:

## Question: What happens when the executable is linked statically? Does valgrind still detect those same bugs?
Ans: Valgrind behaves differently when executables are linked statistically. When we run a statistically linked executable with Valgrind, its memory checks may not work as effectively as with dynamically linked programs. Some memory issues might still be detected.

## Question: Why or Why not?
Ans: Valgrind is primarily designed to work with dynamically linked executables. Valgrind works by modifying the binary code of a program to track memory usage. This is applied to the dynamically linked libraries. However, in statistically linked program, the libraries are included with the executables. Thus, stastically linked executables limit Valgrind's ability to monitor dynamic memory behavior.

