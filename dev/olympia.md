```bash
cmake -S . -B build -G Ninja -D CMAKE_BUILD_TYPE=Release \
-D CMAKE_CXX_COMPILER_LAUNCHER=ccache \
-D SPARTA_SEARCH_DIR=${HOME}/rv/map/sparta/install
```

```bash
cmake -S . -B build -G Ninja -D CMAKE_BUILD_TYPE=Debug \
-D CMAKE_CXX_COMPILER_LAUNCHER=ccache \
-D SPARTA_SEARCH_DIR=${HOME}/rv/map/sparta/install
```

```bash
cmake --build build/ -j $(nproc)
```

```bash
cmake --install build/ --prefix $(pwd)/install
```

```bash
Vector_test -l top info unsupported.out \
-c test_cores/test_big_core.yaml --input-file vrgather.json
```

```bash
./olympia traces/dhry_riscv.zstf --arch small_core \
--report-all dhry_small.report
```

```bash
cmake --build build/ -t Vector_test -j $(nproc)
```

```bash
cmake --build build/ -t regress -j $(nproc)
```

```bash
./olympia -l top info ../rvv_samples/mma.log --arch big_core \
--report-all ../rvv_samples/mma.report ../rvv_samples/mma_e32_m1_vta.json
```

Important stats on the simulator

- IPC
- Branch stats (HIT, MISSES)
- CACHE stats 

For vector

- VSET stall
