```bash
cmake -S . -B build -G Ninja -D CMAKE_BUILD_TYPE=Release -D CMAKE_CXX_COMPILER_LAUNCHER=ccache
```

```bash
cmake --build build/ -j $(nproc)
```

```bash
cmake --install build/ --prefix $(pwd)/install
```